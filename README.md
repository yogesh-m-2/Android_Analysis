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

<h3>run activiy without going to app</h3>
1.see the activity in AndroidManifest.xml -> search for AccessCoontrolActivity<br>
start the adb shell<br>
2.am //activity manager<br>
3.am start -a "activity_name" //eg.jakhar.aseem.diva.action.view_creds<br>
4.am start -a "activity_name" --ez "defenition variable" "parameter"<br>

<h3>content provider</h3>
1.adb shell content query --uri "content://..." //find out the content provider name AndroidManifest.xml or anywhere<br>

<h3>set server</h3>
1.download AndroidLabServer<br>
2.run app.py //server has started now.make changes in app so that it gets rooted to this server<br>
//now to hook the api<br>
3.download AndBug<br>
4.andbug shell -p "process_id of the app"<br>
5.classes<br>
6.methods<br>
7.you can monitor activities<br>


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
4.run app.package.list -f facebook - list all packages (app names)<br>
5.run app.package.attacksurface "package_name"<br>
6.run app.activity.info -a "package_name"<br>
7.run scanner.provider.finduris -a "package name" - find content uri<br>
8.run app.provider.query -a "//content name" - to query a content<br>
9.run app.activity.start  --component "package name"  "component name"<br>


<h3>install burp cert</h3>
openssl x509 -inform DER -in ca.der -out ca.pem<br>
openssl x509 -inform PEM -subject_hash_old -in ca.pem | head -1<br>
(Randomnumber)<br>
cp ca.pem (Randomnumber).0<br>
adb root<br>
adb remount<br>
adb push (Randomnumber).0 /data/local/tmp/ <br>
adb shell<br>
cp /data/local/tmp/(Randomnumber).0 /system/etc/security/cacerts/<br>
chmod 644 /system/etc/security/cacerts/(Randomnumber).0<br>
