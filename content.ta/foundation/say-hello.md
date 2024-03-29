
---
title: 'வணக்கம் சொல்லுங்கள்'
weight: 2

---


# முதல் சி திட்டம்

மாறிகள், மாறிலிகள் & திறவுச்சொற்கள் பற்றிய அறிவைக் கொண்டு ஆயுதம் ஏந்தியவுடன், அடுத்த தர்க்கரீதியான படி, அவற்றை ஒருங்கிணைத்து வழிமுறைகளை உருவாக்குவதாகும். இருப்பினும், இதற்கு பதிலாக, எங்கள் முதல் C நிரலை இப்போது எழுதுவோம். நாங்கள் அதைச் செய்தவுடன், அதைப் பயன்படுத்திய வழிமுறைகளை விரிவாகப் பார்ப்போம். முதல் திட்டம் மிகவும் எளிமையானது. இது அசல், ஆண்டுகளின் எண்ணிக்கை மற்றும் வட்டி விகிதம் ஆகியவற்றைக் குறிக்கும் மதிப்புகளின் தொகுப்பிற்கான எளிய வட்டியைக் கணக்கிடுகிறது.

```c
/* Calculation of simple interest */
/* Author: gekay Date: 25/06/2016 */
#include <stdio.h>

int main() {
    int p, n;
    float r, si;
    
    p = 1000;
    n = 3;
    r = 8.5;
    
    /* formula for simple interest */
    si = p * n * r / 100;
    
    printf("%f\n", si);
    
    return 0;
}

```

இப்போது இந்த திட்டத்தை விரிவாக புரிந்துகொள்வோம்.

## சி திட்டத்தின் படிவம்

C நிரலின் படிவம் அதை எப்படி எழுத வேண்டும்/ தட்டச்சு செய்ய வேண்டும் என்பதைக் குறிக்கிறது. அனைத்து C நிரல்களுக்கும் பொருந்தும் C நிரலின் வடிவம் பற்றி சில விதிகள் உள்ளன. இவை பின்வருமாறு:
- சி நிரலில் உள்ள ஒவ்வொரு அறிவுறுத்தலும் தனித்தனி அறிக்கையாக எழுதப்பட்டுள்ளது.
- ஒரு நிரலில் உள்ள அறிக்கைகள் எந்த வரிசையில் செயல்படுத்தப்பட வேண்டும் என்று நாம் விரும்புகிறோமோ அதே வரிசையில் தோன்ற வேண்டும்.
- அறிக்கையின் வாசிப்புத் திறனை மேம்படுத்த இரண்டு வார்த்தைகளுக்கு இடையில் வெற்று இடைவெளிகள் செருகப்படலாம்.
- அனைத்து அறிக்கைகளும் சிறிய எழுத்துக்களில் இருக்க வேண்டும்.
- C கொடுக்கப்பட்ட வரியில் எந்த நிலையில் அறிக்கை எழுதப்பட வேண்டும் என்பதற்கு குறிப்பிட்ட விதிகள் எதுவும் இல்லை. அதனால்தான் இது பெரும்பாலும் இலவச வடிவ மொழி என்று அழைக்கப்படுகிறது.
- ஒவ்வொரு சி அறிக்கையும் அரைப்புள்ளி ( **; )** உடன் முடிவடைய வேண்டும். இவ்வாறு **;** ஒரு ஸ்டேட்மெண்ட் டெர்மினேட்டராக செயல்படுகிறது.

## சி திட்டத்தில் உள்ள கருத்துகள்

நிரலின் நோக்கம் அல்லது நிரலில் உள்ள சில அறிக்கையின் நோக்கத்தை தெளிவுபடுத்த C நிரலில் கருத்துகள் பயன்படுத்தப்படுகின்றன. நிரலின் நோக்கம், அதன் ஆசிரியர் மற்றும் நிரல் எழுதப்பட்ட தேதி ஆகியவற்றைக் குறிக்கும் கருத்துடன் ஒரு நிரலைத் தொடங்குவது ஒரு நல்ல நடைமுறையாகும்.

C நிரலில் கருத்துகளை எழுதும்போது நீங்கள் நினைவில் கொள்ள வேண்டிய சில விஷயங்கள் இங்கே:
- நிரல் பற்றிய கருத்து /* */ இல் இணைக்கப்பட வேண்டும். எனவே, எங்கள் திட்டத்தில் முதல் இரண்டு அறிக்கைகள் கருத்துகள்.
- சில நேரங்களில் ஒரு திட்டத்தில் ஒரு குறிப்பிட்ட அறிக்கை என்ன செய்கிறது என்பது மிகவும் தெளிவாக இருக்காது. அத்தகைய நேரங்களில் ஒரு கருத்தைப் பயன்படுத்தி அறிக்கையின் நோக்கத்தை (அல்லது அறிக்கைகளின் தொகுப்பு) குறிப்பிடுவது பயனுள்ளது. உதாரணத்திற்கு:
  
```c
/* formula for simple interest */
si = p * n * r / 100 ;
```
- Any number of comments can be written at any place in the program. For example, a comment can be written before the

statement, after the statement or within the statement as shown below.
```c
/* formula */si = p * n * r / 100;
 si = p * n * r / 100; /* formula */
 si = p * n * r / /* formula */ 100 ;
```

- **/* .. */** க்குள் எழுதப்பட்ட உரைக்கு சாதாரண மொழி விதிகள் பொருந்தாது. இவ்வாறு நாம் இந்த உரையை சிறிய எழுத்து, மூலதனம் அல்லது கலவையில் தட்டச்சு செய்யலாம். ஏனென்றால், கருத்துகள் புரோகிராமர் அல்லது சக புரோகிராமர்களைப் புரிந்துகொள்வதற்காக மட்டுமே வழங்கப்படுகின்றன மற்றும் தொகுப்பாளரால் முற்றிலும் புறக்கணிக்கப்படுகின்றன.
- கருத்துகளை உள்ளமைக்க முடியாது. இதன் பொருள் ஒரு கருத்தை மற்றொரு கருத்துக்குள் எழுத முடியாது. உதாரணத்திற்கு,
  
```c
/* Cal of SI /* Author: gekay date: 25/06/2016 */*/
```

is invalid.
- A comment can be split over more than one line, as in,
```c
/* This comment has three lines in it */
```

Such a comment is often called a multi-line comment.
- ANSI C permits comments to be written in the following way:
```c
// Calculation of simple interest // Formula
```

## முக்கிய() என்றால் என்ன?


**முதன்மை( )** எந்த C நிரலிலும் ஒரு முக்கிய பகுதியாகும். அதன் நோக்கம் மற்றும் அதன் நுணுக்கங்களைப் புரிந்துகொள்வோம்.
- **முதன்மை( )** என்பது ஒரு செயல்பாடு. ஒரு செயல்பாடு என்பது அறிக்கைகளின் தொகுப்பிற்கான கொள்கலனைத் தவிர வேறில்லை. ஒரு சி நிரலில் பல செயல்பாடுகள் இருக்கலாம். தொடங்குவதற்கு, ஒரே ஒரு செயல்பாட்டைக் கொண்ட நிரல்களில் மட்டுமே கவனம் செலுத்துவோம். இந்த செயல்பாட்டின் பெயர் **முதன்மை( )** ஆக இருக்க வேண்டும், இது வேறு எதுவும் இருக்க முடியாது. கீழே காட்டப்பட்டுள்ளபடி, **main( )** க்கு சொந்தமான அனைத்து அறிக்கைகளும் { } ஜோடி பிரேஸ்களுக்குள் இணைக்கப்பட்டுள்ளன.

int main( ) { அறிக்கை 1 ; அறிக்கை 2 ; அறிக்கை 3 ; }
- ஒரு கால்குலேட்டரில் செயல்படும் விதம் ஒரு மதிப்பை வழங்கும், அதேபோல், C இல் உள்ள செயல்பாடுகளும் ஒரு மதிப்பை வழங்கும். **main( )** செயல்பாடு எப்போதும் முழு எண் மதிப்பை வழங்கும், எனவே **main( )** க்கு முன் **int** உள்ளது. நாம் வழங்கும் முழு எண் மதிப்பு 0. 0 என்பது வெற்றியைக் குறிக்கிறது. எந்த காரணத்திற்காகவும் **main( )** இல் உள்ள அறிக்கைகள் அவற்றின் நோக்கம் கொண்ட வேலையைச் செய்யத் தவறினால், **main( )** இலிருந்து பூஜ்ஜியமற்ற எண்ணை வழங்கலாம். இது தோல்வியைக் குறிக்கும்.
- Turbo C/C++ போன்ற சில கம்பைலர்கள் **main( )** இலிருந்து எதையும் திரும்பப் பெற அனுமதிக்கவில்லை. அத்தகைய சந்தர்ப்பத்தில் நாம் ** void** என்ற முக்கிய சொல்லைக் கொண்டு அதை முன் வைக்க வேண்டும். ஆனால் இது **main( )** செயல்பாட்டை எழுதுவதற்கான தரமற்ற வழி. அத்தியாயம் 8 இல் செயல்பாடுகள் மற்றும் அவற்றின் செயல்பாடுகள் பற்றி விரிவாகப் பேசுவோம்.

## மாறிகள் மற்றும் அவற்றின் பயன்பாடு

மாறிலிகள் மற்றும் மாறிகளை தனித்தனியாகக் கற்றுக்கொண்டோம். நமது முதல் C நிரலைக் கொண்டு அவற்றின் முக்கியத்துவத்தைப் புரிந்துகொள்வோம்.
- நிரலில் பயன்படுத்தப்படும் எந்த மாறியும் அதைப் பயன்படுத்துவதற்கு முன்பு அறிவிக்கப்பட வேண்டும். உதாரணத்திற்கு,


```c
int p, n ;/* declaration */
float r, si ;/* declaration */
si = p * n * r / 100 ; /* usage */
```
- In the statement,
```c
si = p * n * r / 100 ;
```

***** மற்றும் **/** ஆகியவை எண்கணித ஆபரேட்டர்கள். C இல் கிடைக்கும் எண்கணித ஆபரேட்டர்கள் **+**, **\-**, ***** மற்றும் **/**. C ஆபரேட்டர்களில் மிகவும் பணக்காரர். C இல் 45 ஆபரேட்டர்கள் உள்ளனர்.

ஆச்சரியம் என்னவென்றால், எக்ஸ்போனென்ஷியேஷன் செய்ய ஆபரேட்டர் இல்லை... ஒரு சீட்டு, ஒரு குழுவால் அல்ல, ஒரு தனிநபரால் சி உருவாக்கப்பட்டது என்பதைக் கருத்தில் கொண்டு மன்னிக்க முடியும்.

## printf( ) மற்றும் அதன் நோக்கம்

திரையில் வெளியீட்டைக் காண்பிப்பதற்கான எந்த அறிவுறுத்தலும் C இல் இல்லை. திரைக்கான அனைத்து வெளியீடுகளும் ஆயத்த நூலக செயல்பாடுகளைப் பயன்படுத்தி அடையப்படுகின்றன. அத்தகைய ஒரு செயல்பாடு **printf(** **)**. எங்கள் நிரலைப் பொறுத்து இந்த செயல்பாட்டைப் புரிந்துகொள்வோம்.
- **si** இன் மதிப்பு கணக்கிடப்பட்டவுடன் அது திரையில் காட்டப்பட வேண்டும். அவ்வாறு செய்ய **printf( )** ஐப் பயன்படுத்தியுள்ளோம்.
- நாம் **printf( )** செயல்பாட்டைப் பயன்படுத்த, நிரலின் தொடக்கத்தில் **#include <stdio.h>** ஐப் பயன்படுத்துவது அவசியம். **#include** என்பது ஒரு முன்செயலி உத்தரவு. அதன் நோக்கம் அத்தியாயம் 8 இல் தெளிவுபடுத்தப்படும். இப்போதைக்கு, நீங்கள் **printf( )** ஐப் பயன்படுத்தும் போதெல்லாம் அதைப் பயன்படுத்தவும்.
- **printf( )** செயல்பாட்டின் பொதுவான வடிவம்,

```c
printf ( "<format string>", <list of variables> ) ;

<format string> can contain,
```
**%f** உண்மையான மதிப்புகளை அச்சிடுவதற்கு **%d** முழு எண் மதிப்புகளை அச்சிடுவதற்கு **%c** எழுத்து மதிப்புகளை அச்சிடுவதற்கு

**%f**, **%d** மற்றும் **%c** போன்ற வடிவமைப்பு குறிப்பான்களுக்கு கூடுதலாக, வடிவமைப்பு சரத்தில் வேறு ஏதேனும் எழுத்துகள் இருக்கலாம். **printf( )** செயல்படுத்தப்படும் போது இந்த எழுத்துக்கள் அச்சிடப்படும்.
- **printf( )** செயல்பாட்டின் பயன்பாட்டின் மேலும் சில எடுத்துக்காட்டுகள் கீழே கொடுக்கப்பட்டுள்ளன:
  
```c
    printf("%f\n", si);
    printf("%d %d %f %f\n", p, n, r, si);
    printf("Simple interest = Rs. %f\n", si);
    printf("Principal = %d\nRate = %f\n", p, r);
```
The output of the last statement would look like this...
```c
Principal = 1000 Rate = 8.500000
```

இந்த அறிக்கையில் ‘\\n’ என்ன செய்கிறது? இது புதிய வரி என்று அழைக்கப்படுகிறது, மேலும் இது கர்சரை அடுத்த வரிக்கு கொண்டு செல்கிறது. எனவே, நீங்கள் வெளியீட்டை இரண்டு வரிகளாகப் பிரிக்கலாம். '\\n' என்பது C இல் கிடைக்கும் பல எஸ்கேப் சீக்வென்ஸில் ஒன்றாகும். இவை அத்தியாயம் 18 இல் விரிவாக விவாதிக்கப்பட்டுள்ளன. இப்போது, ​​நாம் அனைத்தையும்

தனித்தனி வரிகளில் வெளியீட்டை சரியாக வடிவமைக்க விரும்பினால், '\\n' பயனுள்ளதாக இருக்கும்.
- **printf(** **)** மாறிகளின் மதிப்புகளை மட்டும் அச்சிட முடியாது, அது ஒரு வெளிப்பாட்டின் முடிவையும் அச்சிட முடியும். ஒரு வெளிப்பாடு என்பது மாறிலிகள், மாறிகள் மற்றும் ஆபரேட்டர்களின் சரியான கலவையைத் தவிர வேறில்லை. எனவே, 3, 3 + 2, c மற்றும் a + b * c – d அனைத்தும் சரியான வெளிப்பாடுகள். இந்த வெளிப்பாடுகளின் முடிவுகளை கீழே காட்டப்பட்டுள்ளபடி அச்சிடலாம்.
  
```c
printf ( "%d %d %d %d", 3, 3 + 2, c, a + b * c – d ) ;
```

**3** மற்றும் **c** ஆகியவை சரியான வெளிப்பாடுகளைக் குறிக்கின்றன என்பதை நினைவில் கொள்ளவும்.
