[![Build Status](https://secure.travis-ci.org/denniskuczynski/beanstalkd_view.png?branch=master)](http://travis-ci.org/denniskuczynski/beanstalkd_view)

A Sinatra app to view/manage beanstalkd queues that can be embedded in a Rails app similar to what's available in Resque.

To use in a Rails app, include the gem in your Gemfile:

gem beanstalkd_view

Otherwise, gem install beanstalkd_view


Use the following environment variable to specify the location of the beanstalk server:

ENV['BEANSTALK_URL'] = 'beanstalk://localhost/'

===============================
 Embedding in a Rails app
===============================

Add the following to your routes.rb file:

mount BeanstalkdView::Server, :at => "/beanstalkd"


(NOTE: You may mount the server at any path, not just /beanstalkd)

You can then browse to your application path to view information about your beanstalkd tubes, i.e.
http://127.0.0.1:3000/beanstalkd

===============================
 Running from the command line
===============================

Run the beanstalkd_view executable, e.g.

beanstalkd_view

or from a Rails app:

bundle exec beanstalkd_view


(This will use the vegas gem to launch the Sinatra app on an available port.)