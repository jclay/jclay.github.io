---
layout: post
title:  "Generating random passwords using Devise"
date:   2015-04-31
---

Here's several solutions to the use case of creating a user account and assigning a random password to it, allowing the user to set their password when they are ready to activate their account.

[Here](https://github.com/plataformatec/devise/wiki/How-To:-Automatically-generate-password-for-users-\(simpler-registration\)) you can see the method used for slashdot. We can take this a few steps further and allow us to generate a password without having to call any special methods on the user to generate a password.

We use it as follows:

{% highlight ruby %}
# Returns a user with random password set
User.create(email: "joel@jclay.com", generate_password: true)
{% endhighlight %}

I implemented it by adding the following to my User model.

{% highlight ruby %}
class User < ActiveRecord::Base
  before_validation :assign_password
  attr_accessor :generate_password

  private
    def assign_password

      if ["1", true, "true"].include? self.generate_password
        self.password = Devise.friendly_token.first(8)
      end

      true # allows validations to continue
    end

end
{% endhighlight %}
