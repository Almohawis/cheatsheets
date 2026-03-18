# كتابة اكثر من امر بسطر واحد

    <!doctype html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <title>Document</title>
    </head>
    <body>
        <h1>تقدر بأنك تضمن اكثر من كود بسطر واحد</h1>
        <h2><?php echo "Hello"; echo "World";?></h2>
    </body>
    </html>

المخرج

    تقدر بأنك تضمن اكثر من كود بسطر واحد
    HelloWorld

# constants الثوابت

المتغير العادي

    <!doctype html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <title>Document</title>
    <?php
    
    $car = "GMC"
    
    ?>
    
    </head>
    <body>
    
    <h1> <?php echo $car?></h1>
    
    <?php $car = "Toyota"?>
    
    <h1> <?php echo $car?></h1>
    
    </body>
    </html>

المخرج

    GMC
    Toyota

كذا تغير المتغير

اما الثوابت

    <!doctype html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <title>Document</title>
    <?php
    
    $car = "GMC";
    define('car', 'Nissan'); // ================================
    ?>
    
    </head>
    <body>
    
    <h1> <?php echo $car?></h1>
    
    <?php $car = "Toyota"?>
    
    <h1> <?php echo $car?></h1>
    
    <h1><?php echo car ?></h1>
    
    </body>
    </html>

المخرج

    GMC
    Toyota
    Nissan

بينما كلهم متغير؟ لكن الديفاين يكتب بدون علامة دولار

# المقارنات

== تقارن بدون الإعتبار لوضع البيانات

=== تقارن مع وضع الاعتبار لوضع البيانات

# switch

    $Name = "Ahmad";
    
    switch ($Name) {
        case "Ahmad":
            echo "welcome Ahmad";
            break;
        case "Lolo":
            echo "welcome Lolo";
            break;
        default:
            echo "welcome Back";

Output Is  `welcome Ahmad`

# ترتيب المصفوفات ---- يبيلها مراجعه

للمفاتيح

    $pepole = [
        ['name' => 'Amal', 'age' => 22, 'address' => 'saudi'],
        ['name' => 'ali', 'age' => 34, 'address' => 'uae'],
        ['name' => 'abdullah', 'age' => 52, 'address' => 'Plasten'],
        ['name' => 'Mogeeb', 'age' => 14, 'address' => 'halab'],
    ];
    sort($pepole)

يرتب من الألف الى الياء

    rsort

من الياء الى الألف

    asort($pepole)

ترتيب على حسب القيمة

    arsort($pepole)

عكسي على حسب القيمة





# فلترة المدخلات

اذا كان نوع التصفية فيه "VALIDATE" معناه يرجع قيمة Boolean.

اذا كان نوع التصفية فيه "SANITIZE" معناه يرجع المدخل نفسه بعد الفلترة.





# include VS require




