# Правила написания разметки экранов

### Стили
>View должно содержать в тэгах id, layout_height, layout_width, padding*, layout_margin*, привязки ConstraintLayout'a, всё остальное - лежит в стилях. Одна строка - один стиль.

>##### Bad:
```xml
<TextView android:id="@+id/txtTitle"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="55dp"
        android:fontFamily="@string/roboto_medium"
        android:textAlignment="inherit"
        android:textColorHint="@color/colorPrimary"
        android:textColorHighlight="@color/colorPrimary"
        android:textColorLink="@color/colorPrimary"
        android:textStyle="bold"
        android:textDirection="firstStrongLtr"
        android:textCursorDrawable="@drawable/ic_done"
        android:freezesText="false"
        android:textAllCaps="true"
        android:textColor="@color/colorText"
        android:textSize="20sp" />
```

>##### Good:

```xml
<TextView android:id="@+id/txtTitle"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="55dp"
        style="@style/TextViewTitleStyle" />
        
<style name="TextViewTitleStyle">
    <item name="android:fontFamily">@string/roboto_medium</item>
    <item name="android:textAlignment">inherit</item>
    <item name="android:textColorHint">@color/colorPrimary</item>
    <item name="android:textColorHighlight">@color/colorPrimary</item>
    <item name="android:textColorLink">@color/colorPrimary</item>
    <item name="android:textStyle">bold</item>
    <item name="android:textDirection">firstStrongLtr</item>
    <item name="android:textCursorDrawable">@drawable/ic_done</item>
    <item name="android:freezesText">false</item>
    <item name="android:textAllCaps">true</item>
    <item name="android:textColor">@color/colorText</item>
    <item name="android:textSize">20sp</item>
</style>
```
### Плейсмент id во View
>android:id атрибут должен располагаться сразу же после класса View.

>##### Bad:
```xml
<TextView android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="55dp"
        style="@style/TextViewTitleStyle"
        android:id="@+id/txtTitle"/>
```

>##### Good:
```xml
<TextView android:id="@+id/txtTitle"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="55dp"
        style="@style/TextViewTitleStyle" />
```

### Общие правила разметки 
>View отделяются от нижележащих View одной строкой. Вложенные View отделяются друг от друга одной строкой и символом табуляции.

>##### Bad:
```xml
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    
    <android.support.design.widget.AppBarLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content">
            <android.support.v7.widget.Toolbar android:id="@+id/toolbar"
            android:layout_width="match_parent"
            android:layout_height="?android:attr/actionBarSize"
            android:background="@color/colorPrimary"
            android:theme="@style/AppTheme.AppBarOverlay"/>
    </android.support.design.widget.AppBarLayout>

    <FrameLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:id="@+id/ltContainer"/>

</LinearLayout>
```

>##### Good:
```xml
<LinearLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical" 
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <android.support.design.widget.AppBarLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content">

        <android.support.v7.widget.Toolbar android:id="@+id/toolbar"
            android:layout_width="match_parent"
            android:layout_height="?android:attr/actionBarSize"
            android:background="@color/colorPrimary"
            android:theme="@style/AppTheme.AppBarOverlay"/>

    </android.support.design.widget.AppBarLayout>

    <FrameLayout android:id="@+id/ltContainer"
        android:layout_width="match_parent"
        android:layout_height="match_parent"/>

</LinearLayout>
```

