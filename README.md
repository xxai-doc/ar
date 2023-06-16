<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

# xxAI.art

جزء من كود موقع الويب مفتوح المصدر ، مرحبًا بك للمساعدة في تحسين الترجمة.

## كود الواجهة الأمامية

* [كود الواجهة الأمامية](https://github.com/xxai-art/web)
* [حزم اللغات للموقع ككل](https://github.com/xxai-art/web/tree/main/i18n)
* [حزم اللغات لوحدات تسجيل الدخول](https://github.com/wacpkg/user/tree/main/ui.i18n)
* [التوثيق متعدد اللغات للموقع](https://github.com/xxai-doc)

لغة البرمجة الأمامية هي [@ w5 / coffee_plus](http://npmjs.com/@w5/coffee_plus) ، والتي تضيف بعض الميزات بناءً على بنية coffeescript ، انظر [./coffee_plus.md](./coffee_plus.md) .

## تدويل المواقع والوثائق

بناء على 3 مشاريع التالية

### [@ w5 / mdt](https://www.npmjs.com/package/@w5/mdt)

يمكن أن يشير قالب Markdown ، الذي يحتوي على اللاحقة `.mdt` ، إلى ملفات خارجية ذات بناء جملة مشابه لـ `<+ ./coffee_plus/import.js>` .

[@ w5 / trmd](https://www.npmjs.com/package/@w5/trmd)

لن تقوم ترجمة Markdown بترجمة الرموز والروابط ، وستقوم بتخزين الجمل المترجمة مؤقتًا. إذا تم تعديل الترجمة ولكن لم يتم تعديل النص الأصلي ، فلن يؤدي تنفيذها مرة أخرى إلى استبدال تعديل الترجمة.

[@ w5 / i18n](https://www.npmjs.com/package/@w5/i18n)

ملفات اللغة لترجمة مواقع الويب التي تم إنشاؤها بواسطة `yaml` .
