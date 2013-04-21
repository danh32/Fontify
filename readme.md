#Fontify

Fontify is an Android library project providing drop-in replacements for all Android TextView subclasses, allowing developers to apply custom fonts via xml layouts and/or styles.

##Set Up:
1) Clone Fontify locally 
2) Import library project into Eclipse
3) Add Fontify to your app as a library project

##Usage:
###Getting fonts in place:
1) Put your custom font file in Android's assets folder (assets/fonts/helvetica.ttf)
2) Put the path to your file in your strings.xml for ease of use:
	<string name="FONT_HELVETICA">fonts/helvetica</string>

###Applying fonts:
####In styles/themes:
1) Declare your style in res/values/styles.xml:
    <style name="CustomTextViewStyle">
        <item name="font">@string/FONT_HELVETICA</item>
    </style>
2) Use the Fontify subclass of your TextView:
	<com.danh32.fontify.TextView 
	    android:layout_width="match_parent"
		android:layout_height="wrap_content"
		style="@style/CustomTextViewStyle" />

####In layouts:
1) Add new XML NameSpace to root element of layout:
	xmlns:fontify="http://schemas.android.com/apk/res-auto"
2) Use the Fontify subclass of your TextView:
	<com.danh32.fontify.TextView 
	    android:layout_width="match_parent"
		android:layout_height="wrap_content"
		fontify:font="@string/FONT_HELVETICA" />
		
####In Java:
Use the textView.setFont(String fontPath) or textView.setFont(int resId) method:

	import com.danh32.fontify.TextView;

	public class CustomFontActivity extends Activity {
		@Override
		onCreate (Bundle savedInstanceState) {
			super(savedInstanceState);
		
			TextView tv = new TextView(this);
			tv.setFont(R.string.FONT_HELVETICA);
		}	
	}
