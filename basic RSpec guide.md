# Unit Testing in Rails

In Ruby on Rails, unit testing is an essential part of ensuring the correctness of your application's code. Rails comes with built-in support for testing through a framework called RSpec. 
RSpec is a testing tool for Ruby that is often used with Rails applications for behavior-driven development (BDD).

Here's a basic guide on how to perform unit testing in Ruby on Rails using RSpec:

## Install RSpec:
Add the RSpec gem to your Gemfile and run bundle install:
```ruby
group :development, :test do
  gem 'rspec-rails', '~> 6.0.3'
end
```
Then, run the following commands in your terminal:

```ruby
rails generate rspec:install
```
This command generates the necessary files and configurations for RSpec in your Rails application.

## Create a Model:
Let's assume you have a model called User. You can generate a model with:

```ruby
rails generate model User name:string email:string
```
## Write Unit Tests:
Open the generated file in spec/models/user_spec.rb and write your tests. For example:

```ruby
# spec/models/user_spec.rb

require 'rails_helper'

RSpec.describe User, type: :model do
  it "is valid with valid attributes" do
    user = User.new(name: "John Doe", email: "john@example.com")
    expect(user).to be_valid
  end

  it "is not valid without a name" do
    user = User.new(email: "john@example.com")
    expect(user).to_not be_valid
  end

  it "is not valid without an email" do
    user = User.new(name: "John Doe")
    expect(user).to_not be_valid
  end
end
```
## Run Tests:
Run your tests using the following command:

```ruby
bundle exec rspec
```
This command will execute all the tests in the spec directory.

## Interpret Results:

After running the tests, RSpec will provide output indicating whether the tests passed or failed. If a test fails, you'll get information about what went wrong.
These are basic steps to get you started with unit testing in Ruby on Rails using RSpec. 
Adjustments may be needed based on your application structure and requirements. 
Additionally, you can explore other testing tools and frameworks like Minitest, but RSpec is widely used and has a strong community in the Ruby on Rails ecosystem.

![image](https://github.com/Majd2404/Unit-Testing-RSpec/assets/56276308/4251b291-934b-454a-a495-c3394d3ec53f)
