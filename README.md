### i18n

https://github.com/svenfuchs/i18n

https://github.com/svenfuchs/i18n/wiki/Resources

```
gem install i18n

module I18n::Backend::Transformers
  def translate(*args)
    transform(*args)
  end
  def transform(entry)
  end
end
I18n::Backend::Simple.send(:include, I18n::Backend::Transformers)

require "i18n/backend/fallbacks"
I18n::Backend::Simple.send(:include, I18n::Backend::Fallbacks)

I18n.backend.store_translations(:en, :foo => '', :bar => '')
I18n.backend.store_translateions(:de, :bar => '')

I18n.backend.store_translations(:en, :foo => '', :bar => '')
I18n.bakend.store_translations(:de, :bar => '')

I18n.translate(:foo, :locale => :de, :default => :bar)
I18n.translate(:foo, :locale => :de, :default => :missing_foo)











config.assets.initialize_on_precompile = false

config.log_level = :warn

def send_devise_notification(notification, *args)
  devise_mailer.send(notification, self, *args).deliver_later
end

create_table :admin do |t|
  t.string :email
  t.string :encrypted_password
  t.timestamp null: false
end
devise :database_authenticable, :timeoutable
devise_for :admins
before_action :authenticate_admin!
admin_signed_in?
current_admin
admin_session

config.omniauth :github, 'APP_ID', 'APP_SECRET', scope: 'user, public_repo'

class PostsTest < ActionDispatch::IntegrationTest
  include Devise::Test::IntegraionHelpers
end
sign_in users(:bob)
sign_in users(:bob), scope: :admin
sing_out :user


```



