# VANTA — قناة تحديثات الكود (Code Packs)

هذا المستودع هو مصدر التحديثات الصغيرة لتطبيق VANTA (أندرويد).

- `manifest.json` — آخر إصدار: الرقم، رابط الحزمة، بصمة SHA-256، الحجم، الملفات.
- `pack-<version>.zip` — حزمة ملفات بايثون (عادة بضعة كيلوبايت).

## كيف يستخدمها التطبيق

في التطبيق: زر 👤 ← «🔄 تحديث الكود (كيلوبايت)» ← ضع رابط manifest:

```
https://raw.githubusercontent.com/MohammedRedaVIP/vanta-updates/main/manifest.json
```

ثم «تحقق» ← «تطبيق». التطبيق يتحقق من SHA-256 قبل التطبيق، ويأخذ نسخة احتياطية،
ويستطيع التراجع بزر واحد.

## كيف تُبنى الحزمة

```bash
python tools/make_pack.py old_src new_src out --version 1.0.7 \
    --base-url https://raw.githubusercontent.com/MohammedRedaVIP/vanta-updates/main
```

المخرجات: `pack-1.0.7.zip` + `manifest.json`. ارفعهما هنا (أو عبر release).

## ملاحظة أمنية

الحزم تحتوي كوداً يُنفَّذ. لا ترفع هنا إلا ما بنيتَه بنفسك، وتأكد من بصمة SHA-256.
