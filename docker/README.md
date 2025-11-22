# البداية

من اجل التحقق هل تثبيت دوكر كان صحيح ننفذ امر

`docker run hello-world`

اذا ظهرت لك هذي الرسالة

`Hello from Docker!
This message shows that your installation appears to be working correctly.`

فيعني ان تثبيتك سليم



## docker create

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

docker run -d -name WebServer-1 nginx

كذا بينشأ لي حاوية بإسم WebServer-1 ويشغلها بدون ما يظهر لي الـLogs

واقدر اني احدد البورت

docker run -p Host_Port:Container_Port

مثلا

docker run -p 8080:80 nginx

واقدر اني ادمج الخيارات كذا

docker run -d -p 8080:80 --name WebServer-1 nginx



## docker ps

الأمر هذا يظهر لي الحاويات التي تعمل فقط

شلون اظهر جميع الحاويات التي تعمل و المطفأ؟

`docker ps -a`



مخرجات الأمر

| CONTAINER ID | IMAGE  | COMMAND                  | CREATED   | STATUS | PORTS  | NAMES |
| ------------ | ------ | ------------------------ | --------- | ------ | ------ | ----- |
| رقم الحاوية  | الصورة | اول امر ينفذ بعد التشغيل | متى انشأت | حالتها | المنفذ | الإسم |



# 


