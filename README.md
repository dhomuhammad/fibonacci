Nama : Ridha Muhammad Rifqi

NIM : 312210491

Kelas : TI.22.A5

Mata Kuliah : Pemrograman Mobile 1

Dosen Pengampu : Donny Maulana, S.Kom.,M.M.S.I.

Tugas : Buatlah Method Program java Toast Number, dengan menghasilkan Bilangan Fibonacci



Daftar Isi:
1.	Layout	
2.	Java	
3.	Design	
4.	Hasil Run	
   
Disini, saya akan mengerjakan dan menjelaskan tugas dari mata kuliah "Pemrograman Mobile 1" yaitu membuat sebuah aplikasi untuk menampilkan bilangan Fibonacci. Selain itu saya juga akan merubah sedikit tampilan dari yang diperintahkan pada tugas, yaitu menambah tombol count, number max dan back.

Berikut adalah coding pada menu layout :

-activity_main.xml

<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context="com.example.fibonacci.MainActivity">


    <Button
        android:id="@+id/numberMax"
        android:layout_width="199dp"
        android:layout_height="55dp"
        android:background="@color/colorPrimary"
        android:onClick="numberMax"
        android:text="NumMax"
        android:textColor="@color/white"/>

    <Button
        android:id="@+id/button2"
        android:layout_width="199dp"
        android:layout_height="55dp"
        android:background="@color/colorPrimary"
        android:onClick="CountUP"
        android:text="Count"
        android:textColor="@color/white"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"/>

    <TextView
        android:id="@+id/show_count"
        android:layout_width="407dp"
        android:layout_height="626dp"
        android:background="@color/yellow"
        android:gravity="center_vertical"
        android:text="0"
        android:textAlignment="center"
        android:textColor="@color/colorPrimary"
        android:textSize="160dp"
        android:textStyle="bold"
        app:layout_constraintBottom_toTopOf="@id/button2"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@id/numberMax"
        app:layout_constraintVertical_bias="1.0"
        tools:ignore=",Rtlcompat"/>

    <Button
        android:id="@+id/button3"
        android:layout_width="210dp"
        android:layout_height="56dp"
        android:background="@color/colorPrimary"
        android:onClick="Reset"
        android:text="Back"
        android:textColor="@color/white"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="1.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@id/show_count"
        app:layout_constraintVertical_bias="0.0"/>

    <Button
        android:id="@+id/button"
        android:layout_width="214dp"
        android:layout_height="50dp"
        android:background="@color/colorPrimary"
        android:text="Edit Text"
        android:textColor="@color/white"
        tools:layout_editor_absoluteX="202dp"
        tools:layout_editor_absoluteY="0dp" />
</androidx.constraintlayout.widget.ConstraintLayout>


-Strings.xml
<resources>

        <string name="app_name">My Application</string>
        <string name="button_label_toast">Toast</string>
        <string name="button_label_count">Count</string>
        <string name="count_initial_value">0</string>
        <string name="coast_message">Welcome Toast</string>
        <string name="Reset">Reset</string>

</resources>

-Colors.xml
<?xml version="1.0" encoding="utf-8"?>
<resources>

        <color name="black">#FF000000</color>
        <color name="white">#FFFFFFFF</color>
        <color name="colorPrimary">#0000FF</color>
        <color name="yellow">#FFFF00</color>
</resources>

-Java class
Pada Java class MainActivity.java berisi semua coding untuk menjalankan aplikasi. Seperti fungsi untuk tombol-tombol, dialog count, dan dialog back.

*{
    margin: 0;
    padding: 0;
    text-decoration: none;
}
.main {
    width: 100%;
    height: 100vh;
    background-image: linear-gradient(rgba(0, 0, 0, 0.75),rgba(0, 0, 0, 0.75)), url(HOTEL.avif);
    background-size: cover;
    background-position: center;
}
.navbar {
    width: 85%;
    margin: auto;
    padding: 35px 0;
    display: flex;
    align-items: center;
    justify-content: space-between;
}
.logo {
    font-size: 36px;
    color: white;
    font-weight: bold;
    width: 120px;
    cursor: pointer;
}
.navbar ul li {
    list-style: none;
    display: inline-block;
    margin:  0 20px;
    position: relative;
}
.navbar ul li a{
    color: white;
    text-transform: uppercase;
}
.navbar ul li::after {
    content: '';
    height: 3px;
    width: 100%;
    background: green;
    position: absolute;
    left: 0;
    bottom: -5px;
    transition: 0,5s;
}
.navbar ul li:hover::after {
    width: 100%;
}
.content {
    top: 50%;
    width: 100%;
    text-align: center;
    color: white;
    position: absolute;
    transform: translateY(-50%);
}
.content h1 {
    font-size: 80px;
    margin-top: 80px;
}
.content p {
    margin: 20px auto;
    font-weight: 100;
    line-height: 25px;
}
@keyframes blinkcolor {
    30%{
        color: #df4a48;
    }
    70%{
        color: #284454;
    }
    100%{
        color: #389c15;
    }
}

@keyframes moveleft {
    0%{
        transform: translate(0px);
    }
    50%{
        transform: translate(20px);
    }
    100%{
        transform: translate(0px);
    }
}
@keyframes moveright {
    0%{
        transform: translate(0px);
    }
    50%{
        transform: translate(-20px);
    }
    100%{
        transform: translate(0px);
    }
}

.blinkteks .we-install {
    text-align: center;
    font-size: 25px;
}
.blinkteks .we-install a {
    color: #df4a48;
    border-bottom: 1px solid;
    padding: 5px;
	  text-decoration: none;
    position: relative;
    animation-name: blinkcolor;
    animation-duration: 3s;
    animation-iteration-count: infinite;
    animation-fill-mode: both;
}
.blinkteks .we-install a:hover {
    animation-play-state: paused;
}
.blinkteks .we-install a:before {
    content: "\f178";
    font-family: fontawesome;
    position: absolute;
    left: -15%;
    animation-name: moveleft;
    animation-duration: 1s;
    animation-iteration-count: infinite;
    animation-fill-mode: both;
}
.blinkteks .we-install a:after {
    content: "\f177";
    font-family: fontawesome;
    position: absolute;
    right: -15%;
    animation-name: moveright;
    animation-duration: 1s;
    animation-iteration-count: infinite;
    animation-fill-mode: both;
}



-Tampilan Design

![Screenshot 2023-11-03 140305](https://github.com/dhomuhammad/fibonacci/assets/130027527/075acf0a-247e-4113-b626-d609d1de9fc9)


-Hasil Run



https://github.com/dhomuhammad/fibonacci/assets/130027527/58aa93a5-1410-4305-8e5b-5c970095497e




