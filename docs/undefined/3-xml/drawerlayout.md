# DrawerLayout

#### activity\_main.xml

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.drawerlayout.widget.DrawerLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:id="@+id/drawer_layout"
    android:fitsSystemWindows="true"
    tools:openDrawer="start"
    tools:context=".MainActivity">

    <LinearLayout
        android:orientation="vertical"
        android:layout_width="match_parent"
        android:layout_height="match_parent">
        <androidx.appcompat.widget.Toolbar
            android:id="@+id/toolBar"
            android:elevation="4dp"
            android:background="@color/green"
            android:layout_width="match_parent"
            android:layout_height="?attr/actionBarSize">

        </androidx.appcompat.widget.Toolbar>
        <FrameLayout
            android:id="@+id/fragment_container"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            >
        </FrameLayout>
    </LinearLayout>

    <com.google.android.material.navigation.NavigationView
        android:layout_width="wrap_content"
        android:layout_height="match_parent"
        android:id="@+id/nav_view" 
        <!-- nav_menu xml 을 참조 -->
        app:menu="@menu/nav_menu"
        android:layout_gravity="start"
        app:itemIconTint="@color/green"
        <!-- nav_header xml 을 참조 -->
        app:headerLayout="@layout/nav_header"
        >

    </com.google.android.material.navigation.NavigationView>
</androidx.drawerlayout.widget.DrawerLayout>
```

#### nav\_header.xml

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_height="176dp"
    android:orientation="vertical"
    android:background="@color/green"
    android:padding="16dp"
    android:gravity="bottom"
    android:layout_width="match_parent">

    <ImageView
        android:src="@mipmap/ic_launcher"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />
    <TextView
        android:text="PDF 탐색기"
        android:textColor="@color/white"
        android:paddingTop="8dp"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />
    <TextView
        android:text="PDF 탐색기"
        android:textColor="@color/white"
        android:paddingTop="8dp"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />

</LinearLayout>
```

#### nav\_menu.xml

```xml
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android">

    <group android:checkableBehavior="single">
        <item android:id="@+id/nav_home"
            android:icon="@drawable/ic_home"
            android:title="Home">
        </item>
        <item android:id="@+id/nav_internal"
            android:icon="@drawable/ic_storage"
            android:title="내부저장소">
        </item>
        <item android:id="@+id/nav_card"
            android:icon="@drawable/ic_sd"
            android:title="SD 카드">
        </item>
    </group>

    <item android:title="More">
        <menu>
            <item android:id="@+id/nav_about"
                android:title="About"
                android:icon="@drawable/ic_about">

            </item>
        </menu>
    </item>
</menu>

```

#### Activity.kt

```kotlin
// 액션바를 툴바로 설정
setSupportActionBar(binding.toolBar)

// 내비게이션 아이템 클릭 리스너 설정
binding.navView.setNavigationItemSelectedListener(this)

// 토글 네비게이션 바 설정
val toggle = ActionBarDrawerToggle(
    this@MainActivity,
    binding.drawerLayout,
    binding.toolBar,
    R.string.open_drawer,
    R.string.close_drawer
)

binding.drawerLayout.addDrawerListener(toggle)
toggle.syncState()
```

