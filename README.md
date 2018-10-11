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



```



