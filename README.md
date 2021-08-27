# about-layout-oxygen-os

Guide About Phone Like OP7 OxygenOS
        
      
      
  Langsung Sesuai permintaan aja... 
  1.apktool
  2.kopi
  3.ketenangan 🤭😁
  4.Tamvan
  
  Method non pusing", masuk res/layout....
  Cari ( about_layout ) kalo gak ada,  bisa buat sendiri & isi about_layout.xml dengan script di bawah ini 
  
  <?xml version="1.0" encoding="utf-8"?>
<RelativeLayout android:layout_gravity="center_vertical" android:id="@+id/phone_hardware_info" android:layout_width="fill_parent" android:layout_height="wrap_content"
  xmlns:android="http://schemas.android.com/apk/res/android" xmlns:app="http://schemas.android.com/apk/res-auto">
    <ImageView android:id="@+id/phone_image" android:layout_width="110.0dip" android:layout_height="225.0dip" android:layout_marginTop="25.5dip" android:layout_marginBottom="30.0dip" android:src="@drawable/oneplus_7" android:antialias="true" android:scaleType="fitXY" android:layout_centerVertical="true" android:contentDescription="@null" android:layout_marginStart="48.0dip" />
    <LinearLayout android:gravity="center" android:orientation="vertical" android:layout_width="wrap_content" android:layout_height="wrap_content" android:layout_marginTop="25.5dip" android:layout_marginBottom="30.0dip" android:layout_centerVertical="true" android:layout_marginStart="56.0dip" android:layout_marginEnd="46.0dip" android:layout_toEndOf="@+id/phone_image">
        <TextView android:id="@+id/cpu_title" android:layout_width="fill_parent" android:layout_height="wrap_content" android:layout_marginBottom="4.0dip" android:text="@string/oneplus_cpu" style="@style/oneplus_contorl_text_style_subtitle" />
        <TextView android:id="@+id/cpu_message" android:layout_width="fill_parent" android:layout_height="wrap_content" android:layout_marginBottom="12.0dip" android:text="@string/cpu_message" style="@style/oneplus_contorl_text_style_body1" />
        <TextView android:id="@+id/storage_title" android:layout_width="fill_parent" android:layout_height="wrap_content" android:layout_marginBottom="4.0dip" android:text="@string/oneplus_storage" style="@style/oneplus_contorl_text_style_subtitle" />
        <TextView android:id="@+id/storage_message" android:layout_width="fill_parent" android:layout_height="wrap_content" android:layout_marginBottom="12.0dip" android:text="@string/storage_message" style="@style/oneplus_contorl_text_style_body1" />
        <TextView android:id="@+id/camera_title" android:layout_width="fill_parent" android:layout_height="wrap_content" android:layout_marginBottom="4.0dip" android:text="@string/oneplus_camera" style="@style/oneplus_contorl_text_style_subtitle" />
        <TextView android:id="@+id/camera_message" android:layout_width="fill_parent" android:layout_height="wrap_content" android:layout_marginBottom="12.0dip" android:text="@string/camera_message" style="@style/oneplus_contorl_text_style_body1" />
        <TextView android:id="@+id/screen_title" android:layout_width="fill_parent" android:layout_height="wrap_content" android:layout_marginBottom="4.0dip" android:text="@string/oneplus_screen" style="@style/oneplus_contorl_text_style_subtitle" />
        <TextView android:id="@+id/screen_message" android:layout_width="fill_parent" android:layout_height="wrap_content" android:text="@string/screen_message" style="@style/oneplus_contorl_text_style_body1" />
    </LinearLayout>
</RelativeLayout>
  
  ===== > Lanjut di mana kita memanggil layout tsb.... 
  Masuk res/xml cari ( frimware_version.xml )
  === > di bawah line ini
  ============================
  xmlns:android="http://schemas.android.com/apk/res/android" xmlns:settings="http://schemas.android.com/apk/res-auto">
  ============================
  Tambahkan ini 
  <PreferenceScreen android:layout="@layout/about_layout" android:selectable="false" android:key="about_oneplus" />

  ============================ 
  

  
  NOTE !!! Untuk rom non pure seerti ( Havoc, RR, Dll ) biasanya udah tersedia , tinggal cari & repleace dengan line di atas
  
  CLUE === >   Paling utama cek res/xml di layout 
( frimware_version.xml ) & lihat ada preference apa di sana 😊
         BACA & PAHAMI
         

    
    ==== > Lanjut
    res/values/dimens.xml tambahkan ini
    <dimen name="oneplus_contorl_text_size_body1">13.399994sp</dimen>
    <dimen name="oneplus_contorl_text_size_subtitle">12.399994sp</dimen>
    <item type="dimen" name="oneplus_contorl_row_space_1">1.03</item>
    <item type="dimen" name="op_contorl_letter_space_body1">0.0</item>
    <item type="dimen" name="op_contorl_letter_space_subtitle">0.0</item>
    
    ==== > Lanjut
    res/values/style.xml
    <style name="oneplus_contorl_text_style_base">
        <item name="android:breakStrategy">simple</item>
    </style>
    <style name="oneplus_contorl_text_style_body1" parent="@style/oneplus_contorl_text_style_base">
        <item name="android:textSize">@dimen/oneplus_contorl_text_size_body1</item>
        <item name="android:textColor">?android:textColorPrimary</item>
        <item name="android:lineSpacingMultiplier">@dimen/oneplus_contorl_row_space_1</item>
        <item name="android:fontFamily">@android:string/config_headlineFontFamilyMedium</item>
        <item name="android:letterSpacing">@dimen/op_contorl_letter_space_body1</item>
    </style>
    <style name="oneplus_contorl_text_style_subtitle" parent="@style/oneplus_contorl_text_style_base">
        <item name="android:textSize">@dimen/oneplus_contorl_text_size_subtitle</item>
        <item name="android:textColor">?android:textColorSecondary</item>
        <item name="android:fontFamily">@string/oneplus_contorl_font_family_subtitle</item>
        <item name="android:letterSpacing">@dimen/op_contorl_letter_space_subtitle</item>
    </style>
    
    ==== > Lanjut
    res/values/strings.xml
    <string name="oneplus_contorl_font_family_subtitle">sans-serif-medium</string>
    <string name="oneplus_cpu">PROCESSOR</string>
    <string name="oneplus_storage">STORAGE</string>
    <string name="oneplus_camera">CAMERA</string>
    <string name="oneplus_screen">SCREEN</string>
    <string name="cpu_message">SNAPDRAGON™ 675</string>
    <string name="storage_message">6GB RAM + 128GB ROM</string>
    <string name="camera_message">48+13 MP Dual Camera</string>
    <string name="screen_message">IPS LCD 6.30 Display</string>
    
    NOTE !!! Untuk strings , ubah sesuai speek device kalian masing" ☺️ 
    
    Sampe sini masukan bahan yg ane sediakan Done...
    
    
    
    Ini hanya ( Relayout ) inget untuk berkreasi di rom atau stock yg kalian suka & Insyallah ane coba kembangkan via smali, kalau ada waktu....   😉
    
    Jika ada salah kata atau ada yang kurang untuk line dll atau mengalami fc dll , bisa PM & tanyakan ane insyallah ane bantu... 
    
    Bonus , Ane tambahkan Drawable Phone berbagai jenis... 
    Good Luck... 
    Happy Modding 😉😎
    
    
    Big Thanks
=============
 - Allah SWT
 
    Credits Thanks
 =============
 - Anu Bareng ( Group Telegram )
 - Mediatek Android And Dev Reborn ( Fb group )
 - All Admin ( Anu Bareng )
 - All User ( Anu Bareng )
 - Apktool by ( Andro black )
 - Onplus
 - Redmi Note 7 Pro
 - Me @GHDev06 ( Penulis )
