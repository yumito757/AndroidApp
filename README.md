# AndroidApp
{First Android App

using System.IO;
using Android.App;
using Android.OS;
using Android.Widget;



namespace App1
{
    [Activity(Label = "Men's Hair Selector(HOME)", MainLauncher = false, Icon = "@drawable/icon")]
    public class Register : Activity
    {
        //int count = 1;
        private void WriteTextFile()
        {
            var sdCardPath = Android.OS.Environment.ExternalStorageDirectory.Path;
            var filePath = System.IO.Path.Combine(sdCardPath, "MyTextFile.txt");
            DirectoryInfo[] cDirs = new DirectoryInfo(@sdCardPath).GetDirectories();
            var registeremailinput = FindViewById<EditText>(Resource.Id.RegisterEmailInput);

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

}}
