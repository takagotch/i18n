### i18n

https://github.com/svenfuchs/i18n

https://github.com/svenfuchs/i18n/wiki/Resources

https://railsguides.jp/i18n.html

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

I18n.backend.store_translations(:en, :foo => 'Foo in :en', :bar => 'Bar in :en')
I18n.backend.store_translateions(:de, :bar => 'Bar in :de')

I18n.translate(:foo, :locale => :de, :default => :bar)
I18n.translate(:foo, :locale => :de, :default => :missing_foo)

I18n.translate(:foo, :locale => :de, :default => 'Default Foo')
I18n.translate(:missing_foo, :locale => :de, :default => 'Default Foo')

I18n.translate(:foo, :locale => :de, :default => Proc.new {'Default Foo'})
I18n.translate(:missing_foo, :locale => :de, :default => Proc.new('Default Foo'))

I18n.translate(:foo, :locale => :de, :default => 'Default Foo', :fallback => false)

I18n.fallbacks.map(:ca => :"es-ES")
I18n.fallbacks[:ca]

I18n.default_locale = :"en-US"
I18n.fallbacks[:ca]

I18n::Locale::Tag.implementation = I18n::Locale::Tag::Rfc4046

de-Latn-DE-1996-a-ext-x-phonebk-i-kligon
de-Latn-DE-1996-a-ext-x-phonebk
de-Latn-DE-1996-a-ext
de-Latn-DE-1996
de-Latn-DE
de-Latn
de

de-Latn-DE-1996
de-Latn-DE
de-Latn
de

"Content-Type: text/plain; charset=UTF-8\n"
"Content-Transfer-Encoding: 8bit\n"
"Plural-Froms: nplurals=INTEGER; plural=EXPRESSION;\n"
msgid "bye"
msgstr "tchau"
msgid "bunny rabbit adventure"
msgstr "a aventura da coelhinha"
msgid "time for bed!"
msgstr "nana nene!"

require "i18n"
include I18n::Gettext::Helpers
I18n::Backend::Simple.include(I18n::Backend::Gettext)
I18n.load_path << Dir["*.po"]
I18n.locale = :pt
puts _("bye")
puts _("bunny rabbit adventure")
puts _("bye", :locale => "pt")

require "i18n"
include I18n::Gettext::Helpers
I18n.backend.store_translations(:pt, "See you soon." => "Ate breve.")
I18n.locale = :pt
puts I18n.t "See you soon."
puts _("See you soon.")

#in locales/fa.rb
{ :fa => { :i18n => { :plural => { :rule => lambda { |n| :other } } } } }

require "i18n/backend/pluralization"
I18n::Backend::Simple.send(:include, I18n::Backend::Pluralization)



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



