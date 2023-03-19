# 기본 세팅

### 최초 1회 세팅
  Flutter.download("*.zip")
  .then(unpacking());
  
  환경변수.Path.add("~/flutter/bin");
  
  AndroidStudio.download().install()
  .then(runSDKManager.SDKTools.AndroidSDKCommandLineTools = true, () => { apply() });
  
  GoogleChrome.download();
  
  openCmd.command("flutter doctor").submit();
  
  AndroidStudioPlugin.install("Flutter");
  
  new Project(select("Flutter"), setSDKPath("~/flutter"));

  File("analysis_option.yaml")["rules"] = {{prefer_typing_uninitialized_variables : false}, 
                                           {prefer_const_constructors_in_immutables : false},
                                           {prefer_const_constructors : false}, 
                                           {avoid_print : false}};

### App 기본 세팅

stless : StatelessWidger을 상속받은 클래스를 생성.
