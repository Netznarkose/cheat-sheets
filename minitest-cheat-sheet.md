## Setup
`unset HOST`  
`export API_SECRET_TOKEN=whatevercomestoyourmind`

## Integrationtest  
place a `save_page` or `screenshot` before running the test  
`open tmp/capybara  

## Run a Minitest

### run a mini-test-file  
`cd backend`  
`bundle exec rake test TEST=test/functional/bl/backend/products_controller_test.rb`  

### run a single mini-test
`bundle exec rake test TEST=test/functional/bl/backend/products_controller_test.rb TESTOPTS="--name=test_product_edit_redirect -v"`  

### run a folder of files  
`rake test TEST=test/features/foobar/*.rb`  

### run a nested folder of files
`rake test TEST=test/features/**/*.rb`  

## Assert a Minitest

### expect redirect  
`assert_response :redirect`  

## Write a Minitest

### point to controller name-space  
```ruby
class AuthorizedUserTest < ActionController::TestCase
  tests Bl::Backend::ProductsController
end
```

### set a scope in minitest
```ruby
rmodule Bl
  module Backend
    module ProductsControllerTest
      class AuthorizedUserTest < ActionController::TestCase
        tests Bl::Backend::ProductsController

        def setup
          authorized_user = create(:superadmin)
          sign_in :bl_user, authorized_user
        end
      end
    end
  end
end
```
### Stub a Mailer in a functional test  
```ruby
def test_confirm_producttests_use_producttest_participation_mailer
 producttest = create(:producttest)
 user = create(:user, notify_me: true)
 r = create(:participation_request, user: user, group: producttest)

 object = stub(confirm: true)
 Bl::Backend::ProducttestParticipationRequestMailer.expects(:delay_for).returns(object)
 bl_put :confirm, user_id: r.user.id, request_id: r.id
end
```

### sequence provides subsequent row of numbers for the sake of ununiq data-sets
```ruby
FactoryGirl.define do
  factory :um_user, parent: :user do
    sequence :um_account_number do |n|
      12345 + n
    end
  end
end
```

### Stub a Constant  

[minitest-stub-const](https://github.com/adammck/minitest-stub-const)  
```ruby
module Foo
  BAR = :original
end

Foo.stub_const(:BAR, :stubbed) do
  Foo::BAR
end
# => :stubbed

Foo::BAR
# => :original
```
