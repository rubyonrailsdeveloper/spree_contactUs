# SpreeContactUs 
[![Build Status](https://secure.travis-ci.org/spree-contrib/spree_contact_us.png)](http://travis-ci.org/spree-contrib/spree_contact_us) [![Dependency Status](https://gemnasium.com/spree-contrib/spree_contact_us.png?travis)](https://gemnasium.com/spree-contrib/spree_contact_us)
A Rails 4+ Engine providing a basic contact form as a Spree Extension.

[travis]: http://travis-ci.org/spree-contrib/spree_contact_us
[gemnasium]: https://gemnasium.com/spree-contrib/spree_contact_us

Modified version of the `contact_us` gem to work with Spree.

## REQUIREMENTS

SpreeContactUs requires:

* Spree Core 3.1 or greater
* Ruby 2.2.0 or greater.

## INSTALLATION

In your `Gemfile`, add the following dependencies:

    gem 'spree_contact_us', :git => 'https://github.com/spree-contrib/spree_contact_us'

From `Rails.root` run:

    $ bundle
    $ bundle exec rails g spree_contact_us:install

In `config/initializers/spree_contact_us.rb` modify:

    config.mailer_to = "contact@please-change-me.com"

Change to the email address you would like to receive the form submissions at for example:

    config.mailer_to = "contact@yourdomain.com"

By default the emails from field will be the email entered by the user to easily reply, but this may not be allowed if your required to verify your sending email addresses.
You may also specify an email address for the notification emails from field:

    config.mailer_from = "dontreply@yourdomain.com"

## CONFIGURATION

If you would like to add a name or subject field to the form you may simply set the options to true within the spree_contact_us initializer located at `config/initializers/spree_contact_us.rb`:

    config.require_name = true
    config.require_subject = true

You may also update your locales under `config/locales/spree_contact_us.en.yml` or create your own.  Please feel free to submit your own locales so that other users will hopefully find this gem more useful.

#### ADD A CONVERISION TRACKING CODE

If you need to print a conversion tracking code on contact sent, you can setup a spree preference for this. Just open a Rails console in your application and launch:

    Spree::ContactUs::Config[:contact_tracking_message] = 'nothing special'

Everything that is not an empty string will cause a flash ("contact_tracking") message to be created. You can use it somewhere in your layout like this:

    <% if flash[:contact_tracking] %>
        put your conversion tracking code here
    <% end %>

By default the preference has an empty string value so no flash messages will be created until you don't need it.

## USAGE

Visit your website and navigate to `/contact-us` to see the form in action.

Be aware that stylesheet customization would be required as the contact-us class does not automatically inherit all the necessary styles.

Refer to [Spree Guide](https://guides.spreecommerce.com/developer/asset.html) on how to go about it.

## ISSUES

Please report any bugs or feature requests to the Github issues page @ https://github.com/spree-contrib/spree_contact_us/issues

## Testing

Be sure to bundle your dependencies and then create a dummy test app for the specs to run against.

    $ bundle
    $ bundle exec rake test_app
    $ bundle exec rspec spec

## TODO

* Modify settings within the admin
* Add new language translations

## CONTRIBUTING

In the spirit of [free software](http://www.fsf.org/licensing/essays/free-sw.html), **everyone** is encouraged to help improve this project.

Here are some ways *you* can contribute:

* by using prerelease versions
* by reporting bugs
* by suggesting new features
* by [translating to a new language](https://github.com/spree-contrib/spree_contact_us/tree/master/config/locales)
* by writing or editing documentation
* by writing specifications
* by writing code (**no patch is too small**: fix typos, add comments, clean up inconsistent whitespace)
* by refactoring code
* by resolving [issues](https://github.com/spree-contrib/spree_contact_us/issues)
* by reviewing patches

## Donating

Bitcoin donations may be sent to: 15VHpDKWpuu8XyPpbTbRbewSRzMu5cVBMr

Copyright (c) 2012-2013 Jeff Dutil, released under the [New BSD License](https://github.com/spree-contrib/spree_contact_us/tree/master/LICENSE).
