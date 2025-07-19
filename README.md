
# WordPress Version Remover

این یک افزونه کوچک و کاربردی برای وردپرس است که به شما کمک می‌کند تا شماره نسخه وردپرس را از کدهای تولید شده توسط تابع `the_generator` حذف کنید. حذف شماره نسخه وردپرس یک اقدام امنیتی توصیه شده است، زیرا از افشای اطلاعات غیرضروری درباره سایت شما جلوگیری می‌کند و می‌تواند به محافظت در برابر حملات هدفمند کمک کند.

## چرا باید شماره نسخه وردپرس را حذف کنید؟

* **امنیت بیشتر:** نمایش شماره نسخه وردپرس می‌تواند به مهاجمان احتمالی اطلاعاتی درباره آسیب‌پذیری‌های شناخته شده در آن نسخه خاص بدهد. با حذف آن، یک لایه امنیتی اضافی به سایت خود اضافه می‌کنید.
* **پنهان‌کاری:** کمک می‌کند تا اطلاعات کمتری درباره پیکربندی سایت شما در دسترس عموم قرار گیرد.

## نصب

برای استفاده از این کد، چند روش وجود دارد:

### روش ۱: به عنوان یک افزونه مستقل

1.  یک پوشه جدید با نام `wp-version-remover` در مسیر `wp-content/plugins/` سایت وردپرسی خود ایجاد کنید.
2.  یک فایل به نام `wp-version-remover.php` در داخل این پوشه ایجاد کنید.
3.  کد زیر را در فایل `wp-version-remover.php` کپی کنید:

    ```php
    <?php
    /**
     * Plugin Name: WordPress Version Remover
     * Description: Removes the WordPress version number from the generator tag for enhanced security.
     * Version: 1.0
     * Author: Your Name (Optional)
     */

    function almasweb_version_remove_version() {
        return '';
    }
    add_filter('the_generator', 'almasweb_version_remove_version');

    ?>
    ```

4.  وارد پنل مدیریت وردپرس خود شوید، به بخش "افزونه‌ها" بروید و افزونه "WordPress Version Remover" را فعال کنید.

### روش ۲: اضافه کردن به فایل functions.php قالب

اگر نمی‌خواهید یک افزونه جدید ایجاد کنید، می‌توانید کد را مستقیماً به فایل `functions.php` قالب فعال خود اضافه کنید. **توصیه می‌شود قبل از انجام این کار از فایل `functions.php` خود یک پشتیبان (backup) تهیه کنید.**

1.  به مسیر `wp-content/themes/YourThemeName/` بروید (به جای `YourThemeName` نام قالب فعال خود را قرار دهید).
2.  فایل `functions.php` را باز کنید.
3.  کد زیر را در انتهای فایل (قبل از تگ بستن `?>` اگر وجود دارد) اضافه کنید:

    ```php
    function almasweb_version_remove_version() {
        return '';
    }
    add_filter('the_generator', 'almasweb_version_remove_version');
    ```

## مشارکت (Contributing)

مشارکت شما خوشایند است! اگر پیشنهاد یا بهبودهایی برای این کد دارید، می‌توانید یک "Pull Request" ایجاد کنید یا "Issue" جدیدی را گزارش دهید.

## مجوز (License)

این پروژه تحت مجوز GPLv2 یا بالاتر منتشر شده است.
