google-alert-api
================

Java Google Alerts API provides you with a lightweight library especially designed to help developers create, delete and update Google alerts within their applications.

<pre>
Latest update on 10/04/2014
Adding language and region feature.
</pre>
--

Required libraries
--
<pre>
commons-logging-1.1.1.jar
httpclient-4.2.1.jar
httpcore-4.2.1.jar
jsoup-1.7.2.jar
</pre>

Usage
--
<pre>
// First of all, we have to login.
GAService service = new GAService("yourGmail", "yourPassword");
// return empty string if login successful else return an error string
service.doLogin();
</pre>
<br>
<pre>
// Get all alerts.
List&lt;AlertBean&gt; lstAlert = service.getAlerts();
</pre>
<br>
<pre>
// Get alert by deliver.
Alert alert = service.getAlertByIdDeliver(DeliverTo.FEED);
</pre>
<br>
<pre>
// Get alert by id.
Alert alert = service.getAlertById(alertId);
</pre>
<br>
<pre>
// Get alert by search query.
List&lt;Alert&gt; lstAlert = service.getAlertsByQuery("Your Query");
</pre>
<br>
<pre>
// Create alert. return an alert id if created successful else return an error string
// Default deliver is email
Alert alert = new Alert();
alert.setHowMany(HowMany.ONLY_THE_BEST_RESULTS);
alert.setHowOften(HowOften.ONCE_A_DAY);
alert.setResultType(ResultType.EVERYTHING);
alert.setSearchQuery("Your Query");
alert.setDeliverTo(DeliverTo.FEED);
alert = service.createAlert(alert);
</pre>
<br>
<pre>
// Delete an alert.
service.deleteAlerts(alertId);
</pre>
<br>
<pre>
// Delete list of alerts.
List&lt;String&gt; lstAlertId = new ArrayList&lt;String&gt;();
lstAlertId.add(alertId);
service.deleteAlerts(lstAlertId);
</pre>
<br>
<pre>
// Update alert. return empty string if updated successful else return an error string
AlertBean alert = new AlertBean();
alert.setId(editAlertId);
alert.setHowMany(HowMany.ONLY_THE_BEST_RESULTS);
alert.setHowOften(HowOften.ONCE_A_DAY);
alert.setSearchQuery("your new query");
alert.setDeliverTo(DeliverTo.FEED);
service.updateAlert(alert);
</pre>
<br>
<pre>
// Get List of alerts need to be verified.
List&lt;Alert&gt; lstAlert = service.getVerifyAlerts();
</pre>
<br>
<pre>
// Verify list of alerts.
List&lt;String&gt; lstAlertId = new ArrayList&lt;String&gt;();
lstAlertId.add(alertId);
service.verifyAlerts(lstAlertId);
</pre>
<br>
Please contact me at nnhiti@gmail.com if you found any issues.<br>
Happy coding.
