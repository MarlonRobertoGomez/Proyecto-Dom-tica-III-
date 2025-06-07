<?xml version="1.0" encoding="utf-8"?> 
<manifest 
    xmlns:android="http://schemas.android.com/apk/res/android" 
    xmlns:tools="http://schemas.android.com/tools"> 
 
    <uses-permission android:name="android.permission.VIBRATE" /> 
    <application 
        android:allowBackup="true" 
        android:dataExtractionRules="@xml/data_extraction_rules" 
        android:fullBackupContent="@xml/backup_rules" 
        android:icon="@drawable/boton" 
        android:label="@string/app_name" 
        android:roundIcon="@mipmap/ic_launcher_round" 
        android:supportsRtl="true" 
        android:theme="@style/Theme.DomoticaApp" 
        tools:targetApi="31"> 
        <activity 
            android:name=".exterior_garaje" 
            android:exported="false" /> 
        <activity 
            android:name=".tercer_piso" 
            android:exported="false" /> 
        <activity 
            android:name=".segundo_piso" 
            android:exported="false" /> 
        <activity 
            android:name=".primer_piso" 
            android:exported="false" /> 
        <activity 
            android:name=".MainActivity" 
            android:exported="false" /> 
        <activity 
            android:name=".pantalla_principal" 
            android:exported="true"> 
            <intent-filter> 
                <action android:name="android.intent.action.MAIN" /> 
                <category android:name="android.intent.category.LAUNCHER" 
/> 
            </intent-filter> 
        </activity> 
    </application> 
</manifest> 

import android.os.Vibrator; 

/ Verificar si el clic largo se realizó en uno de los botones 
específicos 
if (v == foco_pp || v == foco_sp || v == foco_tp || v == foco_ext) 
{ 
// Obtener una referencia al servicio de vibración 
Vibrator vibrator = (Vibrator) 
getSystemService(Context.VIBRATOR_SERVICE); 
// Verificar si el dispositivo soporta la vibración 
if (vibrator != null && vibrator.hasVibrator()) 
{ 
// Duración de la vibración en milisegundos 
final int vibracionDuracion = 100; 
// Hacer vibrar el dispositivo 
vibrator.vibrate(vibracionDuracion); 
}
