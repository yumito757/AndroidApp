# AndroidApp
First Android App


CODE

        if (!System.IO.File.Exists(filePath))
        {
            using (System.IO.StreamWriter sw = new System.IO.StreamWriter("MyTextFile.txt"))
            {


                sw.WriteLine(registeremailinput);


            }
        }
    }
    protected override void OnCreate(Bundle bundle)
    {
        base.OnCreate(bundle);
        // Set our view from the "main" layout resource
        SetContentView(Resource.Layout.RegisterActivity);

        // Get our button from the layout resource,
        // and attach an event to it
        var registerbutton2 = FindViewById<Button>(Resource.Id.RegisterButton2);
        var sdCardPath = Android.OS.Environment.ExternalStorageDirectory.Path;
        Button button = FindViewById<Button>(Resource.Id.RegisterButton2);
        button.Click += delegate
        {
            WriteTextFile();
            registerbutton2.Click += (sender, e) =>
            StartActivity(typeof(MainActivity));
        };



        //Button ONCLICK
        //registerbutton2.Click += (sender, e) => {
        //StartActivity(typeof(MainActivity));


    }
}
