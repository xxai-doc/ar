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

* [@ w5 / mdt](https://www.npmjs.com/package/@w5/mdt)

  اللاحقة هي `.mdt` ، يمكنك استخدام بناء جملة مشابه لـ `<+ ./coffee_plus/import.js>` للإشارة إلى الملفات الخارجية ، وإنشاء علامة التخفيض مع اللاحقة `.md` .

* [@ w5 / trmd](https://www.npmjs.com/package/@w5/trmd)

  لن تقوم ترجمة Markdown بترجمة الرموز والروابط ، وستقوم بتخزين الجمل المترجمة مؤقتًا. إذا تم تعديل الترجمة ولكن لم يتم تعديل النص الأصلي ، فلن يؤدي تنفيذها مرة أخرى إلى استبدال تعديل الترجمة.

* [@ w5 / i18n](https://www.npmjs.com/package/@w5/i18n)

  ملفات اللغة لترجمة مواقع الويب التي تم إنشاؤها بواسطة `yaml` .

### تعليمات أتمتة ترجمة المستندات

انظر المستودع [xxai-art / doc](https://github.com/xxai-art/doc)

يوصى بتثبيت nodejs و [direnv](https://direnv.net) و [bun](https://github.com/oven-sh/bun) أولاً ، ثم تشغيل `direnv allow` بعد دخول الدليل.

من أجل تجنب المستودعات الكبيرة جدًا المترجمة إلى مئات اللغات ، قمت بإنشاء مستودع رموز منفصل لكل لغة وأنشأت منظمة لتخزين هذا المستودع

سيؤدي تعيين متغير البيئة `GITHUB_ACCESS_TOKEN` ثم تشغيل [create.github.coffee](https://github.com/xxai-art/doc/blob/main/create.github.coffee) إلى إنشاء المستودع تلقائيًا.

بالطبع ، يمكنك أيضًا وضعها في المستودع.

مرجع نص الترجمة [run.sh](https://github.com/xxai-art/doc/blob/main/run.sh)

يتم تفسير كود البرنامج النصي على النحو التالي:

[bunx](https://bun.sh/docs/cli/bunx) هو بديل لـ npx ، وهو أسرع. بالطبع ، إذا لم يكن لديك كعكة مثبتة ، فيمكنك استخدام `npx` بدلاً من ذلك.

`bunx mdt zh` يعرض `.mdt` في الدليل zh كـ `.md` ، راجع الملفين المرتبطين أدناه

* [القهوة_plus.mdt](https://github.com/xxai-doc/zh/blob/main/coffee_plus.mdt)
* [القهوة_plus.md](https://github.com/xxai-doc/zh/blob/main/coffee_plus.md)

`bunx i18n` هو الكود الأساسي للترجمة (إذا كان لديك فقط `nodejs` مثبتة ، ولكن لم يتم تثبيت `bun` و `direnv` ، يمكنك أيضًا تشغيل `npx i18n` للترجمة).

سيقوم بتحليل [i18n.yml](https://github.com/xxai-art/doc/blob/main/i18n.yml) ، يكون تكوين `i18n.yml` في هذا المستند كما يلي:

```
en:
zh: ja ko en
```

المعنى هو: الترجمة الصينية إلى الترجمة اليابانية والكورية والإنجليزية والإنجليزية لجميع اللغات الأخرى. إذا كنت تريد دعم اللغة الصينية والإنجليزية فقط ، فيمكنك فقط كتابة `zh: en` .

الأخير هو [gen.README.coffee](https://github.com/xxai-art/doc/blob/main/gen.README.coffee) ، الذي يستخرج المحتوى بين العنوان الرئيسي والعنوان الفرعي الأول لكل لغة `README.md` لإنشاء إدخال `README.md` . الكود بسيط للغاية ، يمكنك النظر إليه بنفسك.

يستخدم Google API للترجمة المجانية. إذا لم تتمكن من الوصول إلى Google ، فيرجى تكوين وكيل وتعيينه ، مثل:

```
export https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7890
```

سينشئ نص الترجمة ذاكرة تخزين مؤقت للترجمة في دليل `.i18n` ، يرجى التحقق منه `git status` وإضافته إلى مستودع الكود لتجنب الترجمات المتكررة.
