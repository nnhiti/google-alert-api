google-alert-api
================

A java library allow user get, create, delete, update google alert.

Usage
--
<pre>
// First of All, we have to login.
GAService service = new GAService("yourEmail", "yourPassword");
service.doLogin();
</pre>
<br>
<pre>
// Get All Alert.
List<AlertBean> lstAlert = service.getAlerts();
</pre>
<br>
<pre>
// Create Alert.
AlertBean alert = new AlertBean();
alert.setHowMany(HowManyBean.ONLY_THE_BEST_RESULTS_VAL);
alert.setHowOften(HowOftenBean.ONCE_A_DAY_VAL);
alert.setResultType(ResultTypeBean.BLOGS_VAL);
alert.setSearchQuery("fakeeeetttbook");
service.createAlert(alert);
</pre>
<br>
<pre>
// Delete Alert.
List<String> lstAlertId = new ArrayList<String>();
lstAlertId.add(alertId);
service.deleteAlerts(lstAlertId);
</pre>
<br>
<pre>
// Update Alert.
AlertBean alert = new AlertBean();
alert.setId(editAlertId);
alert.setHowMany(HowManyBean.ONLY_THE_BEST_RESULTS_VAL);
alert.setHowOften(HowOftenBean.ONCE_A_DAY_VAL);
alert.setSearchQuery("your new query");
service.updateAlert(alert);
</pre>
<br>
Please contact me at nnhiti@gmail.com if you found any issues.
Happy coding.
