MaterialViewPager
=======

[![Build Status](https://travis-ci.org/florent37/MaterialViewPager.svg)](https://travis-ci.org/florent37/MaterialViewPager)
[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-MaterialViewPager-brightgreen.svg?style=flat)](http://android-arsenal.com/details/1/1731)
[![Android Weekly](https://img.shields.io/badge/android--weekly-151-blue.svg)](http://androidweekly.net/issues/issue-151)
[![Join the chat at https://gitter.im/florent37/MaterialViewPager](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/florent37/MaterialViewPager?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

Material Design ViewPager é uma biblioteca fácil de usar

[![Build screen](https://raw.githubusercontent.com/florent37/MaterialViewPager/master/screenshots/screenshot_2_small.png)](http://youtu.be/g6tTDVceM9E)

#Exemplo

Você pode encontrar uma amostra em APK : [Link](https://github.com/florent37/MaterialViewPager/releases/download/1.0.3/sample-debug.apk)

E dá uma olhada no vídeo da amostra no YouTube : [Youtube Link](http://www.youtube.com/watch?v=r95Tt6AS18c)

[![Video](http://i.giphy.com/xTiTnmEsdqa7IZaMXS.gif)](http://www.youtube.com/watch?v=r95Tt6AS18c)

#Download

Em seu módulo [![Download](https://api.bintray.com/packages/florent37/maven/MaterialViewPager/images/download.svg)](https://bintray.com/florent37/maven/MaterialViewPager/_latestVersion)
```groovy
compile ('com.github.florent37:materialviewpager:1.0.4@aar'){
    transitive = true
}
```

#Uso

Adicionar MaterialViewPager para o layout de suas activity's
```xml
<com.github.florent37.materialviewpager.MaterialViewPager
    android:id="@+id/materialViewPager"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    app:viewpager_logo="@layout/header_logo"
    app:viewpager_logoMarginTop="100dp"
    app:viewpager_color="@color/colorPrimary"
    app:viewpager_headerHeight="200dp"
    app:viewpager_headerAlpha="1.0"
    app:viewpager_hideLogoWithFade="false"
    app:viewpager_hideToolbarAndTitle="true"
    app:viewpager_enableToolbarElevation="true"
    app:viewpager_parallaxHeaderFactor="1.5"
    app:viewpager_headerAdditionalHeight="20dp"
    />
```

com **header_logo.xml**
```xml
<?xml version="1.0" encoding="utf-8"?>
<TextView xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/logo_white"
    android:layout_width="wrap_content"
    android:layout_height="@dimen/materialviewpager_logoHeight"
    android:text="Material is Good"
    android:textSize="30sp"
    android:textColor="@android:color/white"/>
```

Você vai ver em Android Studio Preview :

![alt preview](https://raw.github.com/florent37/MaterialViewPager/master/screenshots/preview_small.png)

Para se ter uma bela tela e permitem visualização, você pode adotar tema

```xml
<style name="AppBaseTheme" parent="@style/Theme.AppCompat.Light">
</style>

<style name="AppTheme" parent="AppBaseTheme">

   <item name="android:textColorPrimary">@android:color/white</item>
   <item name="drawerArrowStyle">@style/DrawerArrowStyle</item>
   <item name="android:windowTranslucentStatus" tools:targetApi="21">true</item>

   <item name="android:windowContentOverlay">@null</item>
   <item name="windowActionBar">false</item>
   <item name="windowNoTitle">true</item>

   <!-- Toolbar Theme / Apply white arrow -->
   <item name="colorControlNormal">@android:color/white</item>
   <item name="actionBarTheme">@style/AppTheme.ActionBarTheme</item>

   <!-- Material Theme -->
   <item name="colorPrimary">@color/colorPrimary</item>
   <item name="colorPrimaryDark">@color/colorPrimaryDark</item>
   <item name="colorAccent">@color/accent_color</item>

   <item name="android:navigationBarColor" tools:targetApi="21">@color/navigationBarColor</item>
   <item name="android:windowDrawsSystemBarBackgrounds" tools:targetApi="21">true</item>

</style>

<style name="AppTheme.ActionBarTheme" parent="@style/ThemeOverlay.AppCompat.ActionBar">
    <!-- White arrow -->
    <item name="colorControlNormal">@android:color/white</item>
</style>

<style name="DrawerArrowStyle" parent="Widget.AppCompat.DrawerArrowToggle">
    <item name="spinBars">true</item>
    <item name="color">@color/drawerArrowColor</item>
</style>
```

#Recuperar o MaterialViewPager

Você pode usar MaterialViewPager como um Android View usual, e obtê-lo por findViewById

```java
public class MainActivity extends ActionBarActivity {

    private MaterialViewPager mViewPager;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        mViewPager = (MaterialViewPager) findViewById(R.id.materialViewPager);
    }
}
```

#Personalização

Primeiro, escolha a cor e a altura
```xml
<com.github.florent37.materialviewpager.MaterialViewPager
        android:id="@+id/materialViewPager"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        ...
        app:viewpager_color="@color/colorPrimary"
        app:viewpager_headerHeight="200dp"
        ...
        />
```

##Defina o seu logotipo

```xml
<com.github.florent37.materialviewpager.MaterialViewPager
        ...
        app:viewpager_logo="@layout/header_logo" <-- look custom logo layout
        app:viewpager_logoMarginTop="100dp" <-- look at the preview
        ...
        />
```

###Titlebar Logo

[![Video](http://share.gifyoutube.com/ygbqnA.gif)](http://youtu.be/82gvoUqXb_I)

O layout do seu logotipo deve
* layout_height="@dimen/materialviewpager_logoHeight"

**header_logo.xml**
```xml
<ImageView xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/logo_white"
    android:layout_width="200dp"
    android:layout_height="@dimen/materialviewpager_logoHeight"
    android:fitsSystemWindows="true"
    android:adjustViewBounds="true"
    android:layout_centerHorizontal="true"
    android:src="@drawable/logo_white" />
```

```xml
<com.github.florent37.materialviewpager.MaterialViewPager`
        ...
        app:viewpager_hideLogoWithFade="false"
        ...
        />

```

###Sumindo Logotipo

[![Video](http://share.gifyoutube.com/KYb0D4.gif)](http://youtu.be/9laniARQdqg)

**header_logo.xml**
```xml
<FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="80dp"
    android:layout_height="80dp"
    android:layout_centerHorizontal="true"
    android:background="@drawable/circle">

    <ImageView
        android:layout_width="30dp"
        android:layout_height="30dp"
        android:fitsSystemWindows="true"
        android:adjustViewBounds="true"
        android:layout_gravity="center"
        android:src="@drawable/flying" />
</FrameLayout>
```

```xml
<com.github.florent37.materialviewpager.MaterialViewPager`
        ...
        app:viewpager_hideLogoWithFade="true"
        ...
        />
```

##Toolbar Animation

##Ocultar Logo e Toolbar

[![Video](http://share.gifyoutube.com/y5V8JX.gif)](http://youtu.be/3ElFoqVKxag)

```xml
<com.github.florent37.materialviewpager.MaterialViewPager`
        ...
        app:hideToolbarAndTitle="true"
        ...
        />
```

###Toolbar pegajoso

[![Video](http://share.gifyoutube.com/yo2oJn.gif)](http://youtu.be/3ElFoqVKxag)

```xml
<com.github.florent37.materialviewpager.MaterialViewPager`
        ...
        app:hideToolbarAndTitle="false"
        ...
        />
```

##Tab Bar personalizado

Você pode definir, você possui tab bar, por padrão I, desde 2 implementações

###Padrão

[![Video](http://share.gifyoutube.com/KdnoZX.gif)](http://youtu.be/VRinfxgewNE)

```xml
<com.github.florent37.materialviewpager.MaterialViewPager`
        ...
        app:viewpager_pagerTitleStrip="@layout/material_view_pager_pagertitlestrip_standard"
        ...
        />
```

###News Stand

[![Video](http://share.gifyoutube.com/KeboLp.gif)](http://youtu.be/MBzK2s7HU1A)

```xml
<com.github.florent37.materialviewpager.MaterialViewPager`
        ...
        app:viewpager_pagerTitleStrip="@layout/material_view_pager_pagertitlestrip_newstand"
        ...
        />
```

###Ou criar sua própria barra de abas

Crie o seu próprio layout usando um PagerSlidingTabStrip

**my_tabs.xml**
```xml
<com.astuetz.PagerSlidingTabStrip
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@id/materialviewpager_pagerTitleStrip"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    app:pstsPaddingMiddle="true"
    app:pstsDividerPadding="20dp"
    app:pstsIndicatorColor="#FFF"
    app:pstsIndicatorHeight="2dp"
    app:pstsShouldExpand="true"
    app:pstsTabPaddingLeftRight="10dp"
    app:pstsTextAllCaps="true"
    tools:background="#A333"
     />
```

**Não se esqueça de dar-lhe id="@id/materialviewpager_pagerTitleStrip"**

```xml
<com.github.florent37.materialviewpager.MaterialViewPager`
        ...
        app:viewpager_pagerTitleStrip="@layout/my_tabs"
        ...
        />
```

#Animate Header

[![Video](http://share.gifyoutube.com/yABkgW.gif)](http://youtu.be/90gKwEL1j2I )

Basta ouvir para o ViewPager Page Change e modificar o header's **cor e imagem**

```java
//it's a sample ViewPagerAdapter
mViewPager.setAdapter(new FragmentStatePagerAdapter(getSupportFragmentManager()) {

            int oldPosition = -1;

            @Override
            public Fragment getItem(int position) {
                return RecyclerViewFragment.newInstance();
            }

            @Override
            public int getCount() {
                return 4;
            }

            @Override
            public CharSequence getPageTitle(int position) {
                return "Tab "+position;
            }

            //called when the current page has changed
            @Override
            public void setPrimaryItem(ViewGroup container, int position, Object object) {
                super.setPrimaryItem(container, position, object);

                //only if position changed
                if(position == oldPosition)
                    return;
                oldPosition = position;

                int color = 0;
                String imageUrl = "";
                switch (position){
                    case 0:
                        imageUrl = "http://cdn1.tnwcdn.com/wp-content/blogs.dir/1/files/2014/06/wallpaper_51.jpg";
                        color = getResources().getColor(R.color.blue);
                        break;
                    case 1:
                        imageUrl = "https://fs01.androidpit.info/a/63/0e/android-l-wallpapers-630ea6-h900.jpg";
                        color = getResources().getColor(R.color.green);
                        break;
                    case 2:
                        imageUrl = "http://www.droid-life.com/wp-content/uploads/2014/10/lollipop-wallpapers10.jpg";
                        color = getResources().getColor(R.color.cyan);
                        break;
                    case 3:
                        imageUrl = "http://www.tothemobile.com/wp-content/uploads/2014/07/original.jpg";
                        color = getResources().getColor(R.color.red);
                        break;
                }

                final int fadeDuration = 400;

                //change header's color and image
                mViewPager.setImageUrl(imageUrl,fadeDuration);
                mViewPager.setColor(color,fadeDuration);

            }

        });
```

#Toolbar

```java
Toolbar toolbar = mViewPager.getToolbar();

if (toolbar != null) {
     setSupportActionBar(toolbar);

     ActionBar actionBar = getSupportActionBar();
     actionBar.setDisplayHomeAsUpEnabled(true);
     actionBar.setDisplayShowHomeEnabled(true);
     actionBar.setDisplayShowTitleEnabled(true);
     actionBar.setDisplayUseLogoEnabled(false);
     actionBar.setHomeButtonEnabled(true);
}
```

#ViewPager

```java
ViewPager viewPager = mViewPager.getViewPager();
viewPage.setAdapter(...);

//After set an adapter to the ViewPager
mViewPager.getPagerTitleStrip().setViewPager(mViewPager.getViewPager());
```

#Registrar sua Scrollable

Primeira coisa, sua view e seu fragment de rolagem deve ser **transparent**, so **do not use android:backgound="..."**
Sample :

```xml
<android.support.v7.widget.RecyclerView
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/recyclerView"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    />
```


##RecyclerView

A partir de seu fragment
```java
mAdapter = new RecyclerViewMaterialAdapter(new ***Adapter(mList));
mRecyclerView.setAdapter(mAdapter);

MaterialViewPagerHelper.registerRecyclerView(getActivity(), mRecyclerView, null);
```

###ReyclerView.OnScrollListener

Se você já usa ReyclerView.OnScrollListener (talvez para carga mais, ou qualquer outra coisa)

```java
MaterialViewPagerHelper.registerRecyclerView(getActivity(), mRecyclerView, myRecyclerViewOnScrollListener);
```

Então myRecyclerViewOnScrollListener ainda será notificado

##ScrollView

O ScrollView deve ser um [ObservableScrollView][android-observablescrollview]
```java
MaterialViewPagerHelper.registerScrollView(getActivity(), mScrollView, null);
```

###CallBacks
Se você já usa ObservableScrollViewCallbacks (talvez para carregar mais, ou qualquer outra coisa)

```java
MaterialViewPagerHelper.registerScrollView(getActivity(), mScrollView, myObservableScrollViewCallbacks);
```

Então myObservableScrollViewCallbacks ainda será notificado

###Layout

E deve incluir @layout/material_view_pager_placeholder como primeiro filho
```xml
<com.github.ksoichiro.android.observablescrollview.ObservableScrollView
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:id="@+id/scrollView"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical">

        <include layout="@layout/material_view_pager_placeholder"/>

        ...your content...

    </LinearLayout>
</com.github.ksoichiro.android.observablescrollview.ObservableScrollView>
```

##[Killed for less...] WebView

O WebView deve ser um [ObservableWebView][android-observablescrollview]
```java

//must be called before loadUrl()
MaterialViewPagerHelper.preLoadInjectHeader(mWebView);

//have to inject header when WebView page loaded
mWebView.setWebViewClient(new WebViewClient() {
    @Override
    public void onPageFinished(WebView view, String url) {
        MaterialViewPagerHelper.injectHeader(mWebView, true);
    }
    @Override
    public boolean shouldOverrideUrlLoading(WebView view, String url) {
        view.loadUrl(url);
        return true;
    }
});

mWebView.loadUrl("http://...");

MaterialViewPagerHelper.registerWebView(getActivity(), mWebView, null);
```

#CHANGELOG

##1.0.4
Corrigido :

- Mudança de orientação
- Vazamento de memória
- Android >2.3 com NineOldAndroid
- Uso de ListView removido

##1.0.3

Corrigido :  Resultados do desdobramento rápidas na altura variando Toolbar

RecyclerViewMaterialAdapter pode lidar com um costume células de espaço reservado contar (útil para GridLayoutManager)
```java
public RecyclerViewMaterialAdapter(RecyclerView.Adapter adapter, int placeholderSize)
```

##1.0.2

Atributos adicionados
```java
app:viewpager_parallaxHeaderFactor="1.5"
app:viewpager_headerAdditionalHeight="20dp"
```

*parallaxHeaderFactor* Modificar a velocidade de rolagem de paralaxe do cabeçalho (não a velocidade do efeito KenBurns)
*parallaxHeaderFactor* Configure a altura de o layout do cabeçalho mostrada por trás das primeiras cards view

Corrigido problema quando rolar para baixo  rolar para cima múltiplos tempo, enquanto hideToolbarAndTitle="true"


##1.0.1

Atributos adicionados
```java
viewpager_headerAlpha="0.6"
```

#A FAZER

- Imagem do cabeçalho não carrega toda vez
- **Remover webviews de Android SDK !!!**

#Comunidade

Olhando para os contribuintes, sinta-se livre para forquilhar !

Diga-me se você está usando a minha biblioteca em sua aplicação, vou partilhá-lo neste README

#Dependências

* [Picasso][picasso] (de Square)
* [KenBurnsView][kenburnsview] (de flavioarfaria)
* [Material PagerSlidingTabStrip][pagerslidingtitlestrip] (de jpardogo, forquilhado de astuetz)
* [Android-Observablescrollview][android-observablescrollview] (de ksoichiro)

#Créditos

Autor: Florent Champigny

<a href="https://plus.google.com/+florentchampigny">
  <img alt="Follow me on Google+"
       src="https://raw.githubusercontent.com/florent37/DaVinci/master/mobile/src/main/res/drawable-hdpi/gplus.png" />
</a>
<a href="https://twitter.com/florent_champ">
  <img alt="Follow me on Twitter"
       src="https://raw.githubusercontent.com/florent37/DaVinci/master/mobile/src/main/res/drawable-hdpi/twitter.png" />
</a>
<a href="https://www.linkedin.com/profile/view?id=297860624">
  <img alt="Follow me on LinkedIn"
       src="https://raw.githubusercontent.com/florent37/DaVinci/master/mobile/src/main/res/drawable-hdpi/linkedin.png" />
</a>


Licença
--------

    Copyright 2015 florent37, Inc.

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.


[snap]: https://oss.sonatype.org/content/repositories/snapshots/
[picasso]: https://github.com/square/picasso
[kenburnsview]: https://github.com/flavioarfaria/KenBurnsView
[pagerslidingtitlestrip]: https://github.com/jpardogo/PagerSlidingTabStrip
[android-observablescrollview]: https://github.com/ksoichiro/Android-ObservableScrollView
