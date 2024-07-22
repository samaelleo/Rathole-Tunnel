# رت هول چیست؟

یک پروکسی معکوس امن، پایدار و با کارایی بالا برای عبور از NAT، که با Rust نوشته شده است.

## نحوه ی نصب


اسکریپت زیر را در سرور خود (دبیان یا اوبونتو اجرا کنید)

```
bash <(curl -Ls --ipv4 https://raw.githubusercontent.com/Musixal/rathole-tunnel/main/rathole.sh)
```
ورژن دوم (با ورژن قبلی سازگاری ندارد / پیشنهادی / قابلیت مالتی سرویس و مالتی سرور)

```
bash <(curl -Ls --ipv4 https://raw.githubusercontent.com/Musixal/rathole-tunnel/main/rathole_v2.sh)
```

# نحوه ی کانفیگ 



پس از اجرای اسکریپت از طریق دستور درج شده در بالا


1️⃣ اول باید سرور ایران رو کانفیگ کنید. گزینه ۱ کانفیگ تانل رو بزنید. مجددا گزینه ی ۱ سرور ایران رو انتخاب کنید. ازتون پورت تانل رو میخواد. مثلا ۸۰۸۰ یا ۴۴۳ یا پورت موردنظر خودتون رو بزنید. 
الان تعداد کانفیگ هایی که میخواید تانل کنید و پورتش رو نیاز دارید رو بزنید. مثلا ۲ کانفیگ. به ترتیب پورت کانفیگ ها رو وارد کنید. 
در پایان نوع transport رو انتخاب کنید که tcp یا udp میتونه باشه. 
سرویس در سرور ایران راه اندازی و نصب میشه. با ریستارت سرور هم خودش اجرا میشه. کارمون اینجا تموم شد.

2️⃣ برای سرور خارج بعد از اجرای اسکریپت گزینه ۱ کانفیگ تانل و بعد گزینه ۲ یعنی سرور خارج رو میزنیم. اول تعداد سرورهای ایران رو وارد میکنید. بعد باید آدرس سرور ایران رو وارد کنید. بعد پورت تانل رو میخواد که باید با پورت تانل ایران یکی باشه.
مجددا تعداد کانفیگ ها رو وارد کنید و پورت هایی که تو سرور ایران زدید رو باز همینجا وارد کنید.
سپس نوع transport رو انتخاب کنید که tcp یا udp میتونه باشه. 
اگر تعداد سرور ایران بالای یکی باشه مجددا اطلاعات بالا رو برای سرور بعدی میخواد.
سرویس سرور خارج راه اندازی و نصب میشه.

3️⃣ از طریق گزینه ۳ میتونید وضعیت سرویس رو ببینید. در سرور ایران باید سرویس سرور ایران سبز باشه و سرویس سرور خارج قرمز باشه. در سرور خارج هم سرویس سرور خارج باید سبز و سرویس ایران قرمز باشه، یعنی برعکس هم. اگر هر دو تا قرمز بودند پس یک جای کار ایراد داره. مثلا پورتی رو انتخاب کردید که توسط نرم افزار دیگه داره استفاده میشه. دقت کنید پورت تانل نباید با پورت کانفیگ مشترک باشه.

4️⃣ برای حذف فایل ها و پاکسازی کامل تانل گزینه ۲ یعنی destroy tunnel رو بزنید.

5️⃣ برای ریستارت سرویس های مربوطه گزینه ۵ رو بزنید.

6️⃣ پیشنهاد میشه یه کرون جاب برای ریستارت خودکار سرویس ها ایجاد کنید. برای این کار گزینه ۶ رو بزنید. بعد گزینه ی ۱ اضافه کردن کرون جاب رو بزنید. سرور مدنظر یعنی ایران یا خارج رو انتخاب کنید. تایمی که میخواید ریستارت سرویس انجام بشه رو انتخاب کنید. مثلا برای هر ۶ ساعت عدد ۴ رو بزنید.
برای پاک کردن کرون جاب گزینه ۶ و بعد گزینه ۲ یعنی delete رو انتخاب کنید. اسکریپت فقط کرون جاب خودش رو پاک میکنه و به بقیه کرون جاب هاتون کاری نداره.
کرون جاب رو باید روی هر دو تا سرور ایران و خارج تنظیم کنید و مقدارش هم یک ساعت مشخص باشه. مثلا هر دو تا سرور هر ۶ ساعت باشه.

7️⃣ میتونید روی هر چند تا سرور خارج اسکریپت رو اجرا کنید و همه رو به یک سرور ایران متصل کنید. توی گیت هاب پروژه آموزشش هست.

8️⃣ روی دبیان ۱۲ و اوبونتو تست شده و مشکلی نداره.

🔑 پیشنهاد میکنم برای حفظ امنیت تانلتون  حتما این کار رو انجام بدید.

اسکریپت رو اجرا کنید و  گزینه هفتم یعنی Change security token رو انتخاب کنید. اسکریپت، سرور ایران یا خارج رو خودش تشخیص میده و مقدار فعلی توکن و همچنین یه مقدار رندوم و مطمئن رو بهتون پیشنهاد میده و از شما یه توکن جدید میخواد. توکن رندوم یا هر پسوردی که مدنظرتون هست رو به اسکریپت بدید. بعد از این کار سرویس رت هول به صورت خودکار ریستارت میشه. این مقدار باید در هر دو سرور یکی باشه. پس برای هر دو سرورتون این کار رو انجام بدید و یک توکن واحد رو وارد کنید.



🟢 **نحوه ی تانل چند سرور خارج به یک سرور ایران:**

دقت کنید برای این کار باید پورت تانل بین همه سرورها یکسان باشد. 
 مثلا ۳ سرور خارج دارید. 

0️⃣ در سرور ایران ۳ کانفیگ با مشخصات زیر می سازید. 
شماره پورت ها رو میتونید به دلخواه تغییر بدید:

پورت تانل: ۸۰۸۰ 

پورت کانفیگ ۱:‌ ۲۰۵۳

پورت کانفیگ ۲:‌ ۲۰۵۷

پورت کانفیگ ۳:‌ ۲۰۸۳


1️⃣ برای سرور خارج ۱ فقط یک کانفیگ میزنید:

پورت تانل: ۸۰۸۰ 

پورت کانفیگ:‌ ۲۰۵۳

2️⃣ برای سرور خارج ۲ فقط یک کانفیگ میزنید:

پورت تانل: ۸۰۸۰ 

پورت کانفیگ:‌ ۲۰۵۷

3️⃣ برای سرور خارج ۳ فقط یک کانفیگ میزنید:

پورت تانل: ۸۰۸۰ 

پورت کانفیگ:‌ ۲۰۸۳


به این ترتیب هر پورت به یک سرور خارج تونل میشه. هر چقد سرور خارج داشته باشید میتونید متصل کنید و محدودیتی  نداره. ‌پورت عجیب غریب هم نزنید.

# پورت مانیتور  

چیز خاصی نیست و از طریق اون میتونید ترافیک هر پورت رو تحت نظر داشته باشید. ارتباطی با تانل نداره.
برای این کار گزینه ۶ از منوی اصلی رو انتخاب کنید. بعد گزینه ۱ اضافه کردن پورت ها رو میزنید.

به این صورت میشه پورت اضافه کرد:

`8080, 443, 2058, 2056‍‍`

هر تعداد پورت که نیاز داشت میتونید با کاما جدا کنید و اضافه کنید. بعد هم اگر خواستید میشه مجددا پورت اضافه کرد.

برای مشاهده ترافیک مصرفی گزینه ۶ از منوی اصلی و بعد گزینه ۲ یعنی view traffic usage رو انتخاب کنید.

برای حذف قوانین iptables گزینه ۶ از منوی اصلی و بعد گزینه ۳ رو انتخاب کنید. این اسکریپت فقط قوانین مربوط به خودش رو پاک میکنه و به بقیه قوانین ایجاد شده کاری نداره.


# مشاهده ی Log سرویس 

برای مشاهده ی لاگ سرویس ایران از دستور `journalctl -eu rathole-iran.service` استفاده کنید.

برای مشاهده لاگ سرویس خارج از دستور `journalctl -eu rathole-kharej.service` استفاده کنید.


# تغییر کانفیگ سرویس ها

برای تغییر دستی کانفیگ می تونید در مسیر `root/rathole-core` فایل های کانفیگ با پسوند `toml` رو پیدا و ویرایش کنید. پس از هربار ویرایش برای اعمال تغییرات سرویس برنامه از طریق اسکریپت ریستارت شود.

# اگر تانل شما سرعت پایینی دارد


⁉️ راهکارهایی که میتونید در نظر داشته باشید:

1️⃣ منابع سیستمتون رو چک کنید. درصد CPU Usage یا RAM بالا نباشه. 

2️⃣ اسکریپت Optimizer نصب کنید. BBR مناسب کانفیگ کنید. 

3️⃣ سرعت پورت سرورتون رو با iperf3 چک کنید. ممکنه مشکل از پورت سرورتون باشه. 

4️⃣ پورت تانل و کانفیگ رو عوض کنید، گاها تاثیر خیلی زیادی داره. 

5️⃣ در نهایت اگر هیچکدوم جواب نداد سرورتون رو ریبیلد کنید. 

# منوی اسکریپت
![Menu](https://github.com/Musixal/rathole-tunnel/blob/main/menu_v2.png)




    

# کانال تلگرام من
برای اطلاعات بیشتر کانال زیر را چک کنید:

https://t.me/Gozar_Xray

# حمایت از پروژه


   <a href="https://nowpayments.io/donation?api_key=6Z16MRY-AF14Y8T-J24TXVS-00RDKK7&source=lk_donation&medium=referral" target="_blank">
     <img src="https://nowpayments.io/images/embeds/donation-button-white.svg" alt="Crypto donation button by NOWPayments">
    </a>
    
# سورس کد

https://github.com/rapiz1/rathole
