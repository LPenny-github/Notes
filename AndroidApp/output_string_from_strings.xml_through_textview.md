# output string from strings.xml through textview


1. strings.xml

```
<resources>
    <string name="app_name">Household Chores</string>
    <string name="chore_name1">"擦窗戶"</string>
    <string-array name="chore_name2">
        <item>"洗衣服"</item>
        <item>"刷馬桶"</item>
        <item>"清地板"</item>
        <item>"倒垃圾"</item>
    </string-array>
</resources>
```


2. activity_main.xml

```
<?xml version="1.0" encoding="utf-8"?>
<FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/textview"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Let's do it!"
        android:textSize="20dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</FrameLayout>
```


## resources.getString()


MainActivity.kt

```
class MainActivity : AppCompatActivity() {
        ...

        val textview: TextView = findViewById<TextView>(R.id.textview)
        textview.text = resources.getString(R.string.chore_name1)
    }
}
```


## resources.getStringArray()

MainActivity.kt

```
class MainActivity : AppCompatActivity() {
        ...

        val textview: TextView = findViewById<TextView>(R.id.textview)
        val array: Array<String> = resources.getStringArray(R.array.chore_name2)
        textview.text = array.joinToString()
    }
}
```


## ref

* [String resources/String](https://developer.android.com/guide/topics/resources/string-resource#String)

* [String resources/String array](https://developer.android.com/guide/topics/resources/string-resource#StringArray)

* [joinToString()](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/join-to-string.html)