# Ekran Görüntüsü Engelleme

### Google Arama Kelimesi:
how to block screenshot android app kotlin

#### Araştırken çıkan şeyler:

FileObserver -> Anladığım kadarıyla Screnshot klasörünün içine yeni bir dosya oluşturulursa bunu algılar ve isterseniz silebilirsiniz , isterseniz Snapchat olduğu gibi karşı tarafa bildirim atabilirsiniz ama bu yöntem ile Kotlin dilinde nasıl Ekran görüntüsü almayı engellebileceğimi bulamadım ve Java tarafında gördüğüm kadarıyla uğraştırıyordu.

[Android Developers Dökümasyon sayfası için tıklayın ](https://developer.android.com/reference/kotlin/android/os/FileObserver)

WindowManager -> Google amcaya göre - "Uygulamaların pencere yöneticisiyle konuşmak için kullandığı arayüz."
bana göre geliştirdiğini app'in Activty'de isterseniz Ekran'ı hiç uyku moduna aldırmayın isterseniz Ekran Görüntüsü alınmasın, İsterseniz layout'a geçince app'in düzeni yatay olsun gibi özelleştirmeler yapabiliyorsunuz.

[Android Developers Dökümasyon sayfası için tıklayın ](https://developer.android.com/reference/kotlin/android/view/WindowManager?hl=en)

## Çözüm Yöntem

Android SDK'da Window Manager'in altında FLAG_SECURE adında bir paramatre ile Ekran görüntüsü ve Ekran Kayıt alma engellenebilir.


```kotlin
// Import Package
import android.view.WindowManager 
    
// Ana kod bloğunun içine yerleştirilmesi gereken kod.

window.setFlags(WindowManager.LayoutParams.FLAG_SECURE, WindowManager.LayoutParams.FLAG_SECURE)

```


## Çözüm MainActivity

```kotlin
    package xxx.xx.ekrangoruntusublock  
    import androidx.appcompat.app.AppCompatActivity 
    import android.os.Bundle  
    
    // Import Package
    import android.view.WindowManager  
    
    class MainActivity : AppCompatActivity() {  
    override fun onCreate(savedInstanceState: Bundle?) {  
        super.onCreate(savedInstanceState)  
        // Screenshot ve Ekran Video almayı engelleyen kod bloğu.
        
        window.setFlags(WindowManager.LayoutParams.FLAG_SECURE, WindowManager.LayoutParams.FLAG_SECURE)  
        
        setContentView(R.layout.activity_main) 
    }  
        }
```

# Ekran Görüntüsü

![enter image description here](https://raw.githubusercontent.com/muhammetardayildiz/kotlinnotlarim/main/img/ekrangoruntublock-ss.png)
