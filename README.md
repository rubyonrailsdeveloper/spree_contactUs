## INSTALLATION

In your `Gemfile`, add the following dependencies:

    gem 'spree_contact_us', github: 'rubyonrailsdeveloper/spree_contactUs'

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
