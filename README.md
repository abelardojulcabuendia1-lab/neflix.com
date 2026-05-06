// Source - https://stackoverflow.com/a/32506218
// Posted by guillaume guerin, modified by community. See post 'Timeline' for change history
// Retrieved 2026-05-06, License - CC BY-SA 3.0

try{
  UserAgent userAgent = new UserAgent(); 
  userAgent.visit("http://jaunt-api.com/examples/login.htm");

  userAgent.doc.fillout("Username:", "tom");       //fill out the component labelled 'Username:' with "tom"
  userAgent.doc.fillout("Password:", "secret");    //fill out the component labelled 'Password:' with "secret"
  userAgent.doc.choose(Label.RIGHT, "Remember me");//choose the component right-labelled 'Remember me'.
  userAgent.doc.submit();                          //submit the form
  System.out.println(userAgent.getLocation());     //print the current location (url)
}
catch(JauntException e){
  System.err.println(e);
}

