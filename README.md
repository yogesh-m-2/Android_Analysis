# Android_Analysis

1.adb connect "device ip on the device head..it will be on top"<br>
2.adb devices<br>
3.adb shell<br>
4.cd /data/data <br>

<h3>source code</h3>
1.unzip -d "to the filename" "name of the ap" //normal unzip<br>
2.apktool d "name of the apk"<br>
3.jadx-gui<br>
4.dexdump<br>
5.hexdump<br>
6.dex2jar<br>
7.jd-gui "name of the file class which decompiled using dex2jar"<br>

<h3>Java Debugger</h3>
1.adb jdwp<br>
2.adb shell ps | grep "app_name"<br>
3.adb forward tcp:"process_id(select 3333 if u dont remember)" jdwp:"process_id_of_app"<br>
4.jdp -attach localhost:"process_id(select 3333 if u dont remember)"<br>
5.classes<br>
6.methods "package name eg.jakhar.aseem.diva.NotesProvider"<br>
7.stop in "packagename.method" //here breakpoint will be set <br>
8.resume<br>

<h3>Drozer</h3>
1.adb forward tcp:31415 tcp:31415<br>
2.drozer console connect<br>
3.run "module_name"<br>
4.run app.package.attacksurface "package_name"<br>
