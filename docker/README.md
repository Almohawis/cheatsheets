# البداية

من اجل التحقق هل تثبيت دوكر كان صحيح ننفذ امر

`docker run hello-world`

اذا ظهرت لك هذي الرسالة

`Hello from Docker!
This message shows that your installation appears to be working correctly.`

فيعني ان تثبيتك سليم

# docker hub

هذا ليس أمر بل الموقع اللي تاخذ منه الصور و الحاويات لدوكر

[hub.docker.com](https://hub.docker.com/)

تبحث عن الخدمة المراد تثبيتها وتاخذ المستودع و تثبته

مثال

ubuntu/nginx

ويجب التنبيه انه بهذي الطريقة تحمل اخر اصدار اما اذا كنت تبي اصدار محدد فاكتبه

ubuntu/nginx:1.22-23.04_beta

تحدد الإصدار من الجانب الأيمن تحت اسم

tag summary

# docker search

بالمختصر

docker hub

بس في سطر الأوامر

مثال على الأمر

`docker search SERVICEname`

مثلا

`docker search nginx`

المخرج

| NAME       | DESCRIPTION | STARS                               | OFFICIAL                        |
| ---------- | ----------- | ----------------------------------- | ------------------------------- |
| اسم الصورة | وصف مختصر   | عدد المعجبين ويعطيك فكرة عن الشعبية | اذا كانت صورة رسمية بيكتب لك OK |

لمعلومات اكثر خذ الإسم وابحث عنه في docker hub

# docker create

هذا الأمر ينشأ لك حاوية

`docker create nginx`

كذا بينشأ لي حاوية لـnginx

بيبحث اول شي هل هناك في [DockerHub](https://hub.docker.com/) صورة له؟

اذا كان هناك فبيثبته لك بجهازك

كذا حملي Nginx Web Server

بيختار لي إسم عشوائي فإذا ابي اسمي الحاوية اسم خاص

`docker create --name NAME nginx`

مثلا

docker create --name WebServer-1 nginx

وإذا ابي احدد البورت

docker create -p Host_Port:Container_Port

مثلا

docker create -p 8080:80 nginx

كذا اذا من جهازي دخلت على بورت 8080 بيظهر لي اللي يظهر ببورت 80 بالحاوية

واقدر ادمج الخيارات كذا

docker -d -p 8080:80 --name WebServer-1 nginx

## docker run

وش الفرق بين هذا الأمر والذي قبله؟

هذا الأمر ينشأ لك الحاوية ويشغلها

اما اللي قبل بس ينشأ

ونفس الخيارات لكن بعيد شرحها من اجل ان تكون واضجه

للإنشاء و التشغيل

docker run nginx

طبعا بتفتح لك على الـLogs من اجل ان ترا ان كان هناك اخطاء ام لا فإذا لم ترد هذا الشي نفذ

docker run -d nginx

كذا بينشأ الحاوية وبيشغلها بدون ما يدخلك على الـLogs

وتقدر انك تستخدم اكثر من خيار في امر واحد

docker run -d --name WebServer-1 nginx

كذا بينشأ لي حاوية بإسم WebServer-1 ويشغلها بدون ما يظهر لي الـLogs

واقدر اني احدد البورت

docker run -p Host_Port:Container_Port

مثلا

docker run -p 8080:80 nginx

واقدر اني ادمج الخيارات كذا

docker run -d -p 8080:80 --name WebServer-1 nginx

## 

# docker pull

هذا الأمر يحملك الصورة بدون ما يحولها لك لحاوية

فائدتها والفرق بينها وبين الأمرين السابقين ان الأمرين السابقين يحملون لك الك الصورة بعدها ينشئون لك الحاوية

لكن اذا كنت تبي تكون الصورة متواجده من اجل ان تنشأ حاوية بدون انترنت فتنفذ هذا الأمر

وكذا بتصير الصورة موجوده متى ما بغيت تنشأ الحاوية تنشأها حتى لو ماكان عندك نت

مثال

`docker pull ubuntu/nginx`

كذا بيحملك الصورة بدون ما يحولها لك لحاوية او يشغلها لك

لتحويلها

`docker create OPTIONS ubuntu/nginx`

او لتحوليها و تشغيلها

`docker run OPTIONS ubuntu/ngnix`

# docker images

لمعرفة الصور المثبته واصداراتها

مخرج الأمر

| REPOSITORY | TAG     | IMAGE ID    | CREATED     | SIZE    |
| ---------- | ------- | ----------- | ----------- | ------- |
| المستودع   | الاصدار | معرف الصورة | وقت الانشاء | المساحة |

## docker ps

الأمر هذا يظهر لي الحاويات التي تعمل فقط

شلون اظهر جميع الحاويات التي تعمل و المطفأ؟

`docker ps -a`

مخرجات الأمر

| CONTAINER ID | IMAGE  | COMMAND                  | CREATED   | STATUS | PORTS  | NAMES |
| ------------ | ------ | ------------------------ | --------- | ------ | ------ | ----- |
| رقم الحاوية  | الصورة | اول امر ينفذ بعد التشغيل | متى انشأت | حالتها | المنفذ | الإسم |

# docker start & stop & restart & pause & unpause

هذي بعد ما تستخدم امر

`docker create`

لأنه ينشأ الحاوية بدون تشغيل

او

`docker run`

لأنه ينشأ الحاوية ويشغلها لمرة واحدة بس

اما بعدها تحتاج هذي الأوامر

start = ابدأ

stop  = توقف

restart = اعد تشغيل

pause = توقف مؤقتا

unpause = تراجع عن التوقف المؤقت

بعدها اسم الحاوية او تعريفها

كيف انفذها؟

`docker start Container-Name-Or-ID`

مثلا

`docker start Web-Server-1`

او

`docker restart f1eb15c5f417`

# docker rm

لحذف الحاويات

يجب ان تكون الحاوية مطفأه

docker rm Container-Name-Or-ID

مثلا

`docker rm Web-Server-1`

او

`docker rm f1eb15c5f417`

# docker rmi

لحذف الصور المثبته

يجب ان تكون الحاويات المشغلة بواسطة الصورة المراد حذفها مطفأه

مثال على الأمر

`docker rmi Container-Name-Or-ID`

مثال واقعي

`docker rmi ubuntu/ngnix`

# docker stats

لمراقبة حالة الحاويات ومعدل الإستخدام

| CONTAINER ID  | NAME  | CPU             | MEM USAGE % LIMIT                     | MEM                | NET                              | BLOCK                              | PIDS                      |
| ------------- | ----- | --------------- | ------------------------------------- | ------------------ | -------------------------------- | ---------------------------------- | ------------------------- |
| تعريف الحاوية | الإسم | استخدام المعالج | استخدام الرام مقارنة بالنسبة المسموحة | نسبة استهلاك الرام | حجم البيانات المرسلة و المستقبله | نسبة القراءة والكتابه على الهاردسك | عدد العمليات داخل الحاوية |

# docker logs

لمراقبة سجلات الحاوية

تذكر هذا الأمر؟

`docker run -d`

`-d`

يخفي لك السجلات

لكن اذا اردت ان تقراها فتنفذ هذا الأمر

`docker log Container-Name-Or-ID`

مثال

`docker log Web-Server-1`

تفيدك لحل المشاكل

# docker top

لمراقبة استخدام الحاوية

كأنك نفذت امر

`top`

في نظام لينكس

الإستخدام

`docker top Container-Name-Or-ID`

مثال

`docker top Web-Server-1`

# docker exec

لتنفيذ الأوامر داخل الحاويات

الإستخدام

`docker exec Container-Name-Or-ID COMMAND`

مثال

`docker exec Web-Server-1 apt install php`

اما للدخول على الحاوية نفذ هذا الأمر

`docker exec -it Container-Name-Or-ID bash`

مثال

`docker exec -it Web-Server-1 bash`

# docker diff

لإظهار التغييرات على النسخة الأصلية للحاوية من حذف او انشاء ملفات

لتنفيذ الأمر

`docker diff Container-Name-Or-ID`

مثال

`docker diff Web-Server-1.`

المخرجات تكون كالتالي

- A = اضيف

- C = تغير

- D = حذف

---

# Dockerfile

عدينا مشوار طويل ولا بقي الا القليل "تقريبا" -__- 

ملف دوكر تنشئ منه صورة على حسب احتياجك

يجب ان يكون اسم الملف هكذا

`Dockerfile`

نبدأ

اولا للإستدعاء نستخدم

`FROM BaseImage`

BaseImage = الصورة اللي تبني عليها

مثلا بستدعي نظام ابنتو

`FROM ubuntu:latest`

او مثلا حاب انك تبني على انجنكس

`FROM nginx`

لكن لفهم اكثر بكمل على ابنتو

بعدها عندنا امر

`RUN`

هذا الأمر ينفذ لك الأوامر مثلا

`RUN apt update && apt full-upgrade -y`

تقدر تنفذ الأمر اللي تبيه بشرط مايصير يلزم تدخل منك مثلا لو كان

`RUN apt update && apt full-upgrade`

كذا بتحصل مشكلة بالحاوية لأنه امر

`apt full-upgrade`

يحتاج تدخل من المستخدم بالتأكيد او الإلغاء

فعشان كذا اضفنا `-y`

تطبيق على الشرح السابق

    FROM ubuntu:latest
    RUN apt update && apt full-upgrade -y

بنينا على صورة نظام ابنتو و امرت بتحديث النظام

الآن لتحديد البورت نستخدم

`EXPOSE PortName`

مثلا

`EXPOSE 80`

فمثلا نبي نحمل انجنكس ويب سيرفر على ابنتو واشغله

    FROM ubuntu:latest
    RUN apt update && apt install nginx -y
    EXPOSE 80

كذا فتحنا البورت اللي يستخدمه انجنكس ويب سيرفر

ممتاز, واذا عندي ملف ابي انسخة الى الحاوية؟

مثلا

`index.html`

اول شي لازم نتاكد انه بجانب دوكر فايل بنفس المجلد او بتضطر تحط مساره

نستخدم

`COPY FileName Dire/FileName`

مثلا

`COPY index.html /var/www/html/index.html`

نضيفه الى المثال السابق

    FROM ubuntu:latest
    RUN apt update && apt install nginx -y
    COPY index.html /var/www/html

الآن بيبني الحاوية على صورة ابنتو وبيحدث وبعدها بيحمل انجنكس ويب سيرفر بعدها بينسخ ملف

`index.html`

الى مسار وتحت اسم

`/var/www/html`

من الإستخدامات ايضا تغيير الإعدادات الافتراضية لبرنامج معين  وقس على ذلك وش تقدر تسوي
