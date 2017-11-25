# ProgressWindow_Android

A library to show progress in the toast level above any view or layout in your application.


**Installation**

Add it in your root build.gradle at the end of repositories:

	allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
	
Step 2. Add the dependency

	dependencies {
	        compile 'com.github.mmoamenn:ProgressWindow_Android:0.0.1'
	}


**Example :**

**in your base activity**

   `private ProgressWindow progressWindow ;`

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        progressConfigurations();
    }

**set progress configuration**

    private void progressConfigurations(){
        progressWindow = ProgressWindow.getInstance(this);
        ProgressWindowConfiguration progressWindowConfiguration = new ProgressWindowConfiguration();
        progressWindowConfiguration.backgroundColor = Color.parseColor("#32000000") ;
        progressWindowConfiguration.progressColor = Color.WHITE ;
        progressWindow.setConfiguration(progressWindowConfiguration);
    }

**Functions to show and hide**

    public void showProgress(){
        progressWindow.showProgress();
    }

   
    public void hideProgress(){
        progressWindow.hideProgress();
    }

**Don't miss to make sure hide progress in pause**

    @Override
    protected void onPause() {
        super.onPause();
        hideProgress();
    }
}
