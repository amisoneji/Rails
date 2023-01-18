## Bundler:

Bundler is a dependency management tool available as a gem. You can install it through RubyGems which comes built-in from Ruby 1.9 with gem install bundler. Bundler will read the Gemfile for the list of gems need to be installed, fetches metadata from the source provided, resolves the dependencies of each gem, installs them and requires them while booting. Without bundler, we need to handle the installation and manage the dependencies manually.

## Gemfile:

Gemfile is a ruby file. You can specify the gem dependencies of the project in Gemfile. During the gem installation and while auto requiring the gems, bundler will search for the Gemfile under the directory mentioned by the environment variable BUNDLE_GEMFILE or at the root of the project directory.

Bundler provides a utility called **bundle init** which creates a simple Gemfile on the current working directory with default source as RubyGems. By default a new rails application ships with Gemfile along with the default gems.

## Gemfile.lock:

When you run **bundle install (Or simply bundle)**, bundler will install the gems listed on Gemfile along with their dependencies (Includes the dependencies of dependencies). Bundler will create a file called Gemfile.lock with the list of the gems installed along with versions of the installed gems. Next time when you run bundle install, bundler will read the Gemfile.lock and install the exact same versions of the gems listed on Gemfile.lock. **This makes sure that the application runs with the same version of the gems in all the environments.**

Whenever you install a new gem or remove a gem or updating a gem, the Gemfile.lock will get updated. **Be sure to commit the Gemfile.lock to the version control to avoid breaking your app.**

## Groups:

A gem can be declared under more than one group. Bundler will consider the gems as default group if no gem group specified. On the below Gemfile, gem rails isn’t specified under any group, bundler will consider this gem in default group.

Gemfile

group :development do

gem 'spring'

end

gem 'rails', '5.2.3'

1. By default, bundler will install the gems listed in all the groups. You can override it by passing the option without. It accepts the list of groups to exclude from the installation. Please note that bundler will only skip the installation of the gems. It will still download the gems to exactly resolve the dependencies of the gems listed in the Gemfile.

For example, bundle install –without test will exclude installing the gems from the test group. It will create a file called config under the directory root of the app/.bundle to remember the option. The next time when you bundle install without the without option, bundler will still remember the option from the config file.

.bundle/config

- --

BUNDLE_WITHOUT: "test"

2. Most Rails applications contain few gems which are used only for development and testing. Source code of these gems doesn’t need to be loaded on the production environment. With bundler, you can auto require gems from the specific groups.

**You can also provide a pessimistic version using "->".   
Bundler will increment the last digit of the specified version to identify the range of versions applicable for installation. 
For example gem "rails", "-> 4.2.0" allows installation of rails gem with version ">= 4.2.0" and "< 4.3.x"**

[ARTICLE LINK](https://blog.mallow-tech.com/2019/12/understanding-bundler-gemfile-in-ruby-rails/)
