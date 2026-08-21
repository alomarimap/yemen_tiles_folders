# دليل تصدير البلاطات من Global Mapper

## 1) هيكل المجلدات
ضع كل سنة في مجلدها:
tiles/tiles_1964/{z}/{x}/{y}.png

## 2) خطوات التصدير في Global Mapper
1. افتح الصور الجوية للسنة الواحدة معاً (بعد الجيوريفرنس).
2. تأكد من الإسقاط: Tools > Configure > Projection = Geographic (Latitude/Longitude) WGS84
   ثم عند التصدير اختر Web Mercator إن طُلب.
3. File > Export > Export Raster/Image Format...
4. اختر: "Tiled Web Imagery / TMS-XYZ Tiles" (أو Google Maps Tiles).
5. الإعدادات:
   - Tile Format: PNG (مع Transparent background للمناطق الفارغة)
   - Tile Size: 256 x 256
   - Naming: {zoom}/{x}/{y}.png  (Google/XYZ scheme — ليس TMS المعكوس)
   - Zoom Levels: من 10 إلى 18 (استخدم 19 فقط للصور عالية الدقة)
   - Projection: EPSG:3857 (Web Mercator)
6. مجلد الحفظ: اختر المجلد tiles_YYYY الموافق للسنة.

## 3) ملاحظة مهمة
إن صدّرت بنظام TMS (محور Y معكوس) أخبرني لأضبط الخريطة على tms: true.

## 4) بعد التصدير
انسخ مجلدات tiles_YYYY داخل public/tiles/ في المشروع، وستظهر السنوات تلقائياً في الشريط الجانبي.
