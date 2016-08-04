google-alert-api v2
================

A java library allow user get, create, delete, update google alert.

Compiled with java version 1.7

Issues:
--

Fixed language issue, the language result is incorrect;

Notes:
--
Please see the email that your Google Alert using (may be the alert is using uppercase or lowercase)
So GAService("nnhiti@gmail.com", "pass") will different with GAService("NNHITI@gmail.com", "pass")

Required libraries
--

No required

Usage
--

// First of all, we have to login. return true string if login successful else return false
<pre>
GAService service = new GAService("yourGmail", "yourPassword");
service.doLogin();
</pre>

--
// Get all alerts.

<pre>
List<Alert> lstAlert = service.getAlerts();
</pre>

--
// Get alert by delivery.

<pre>
List<Alert> lstAlert = service.getAlertByDelivery(DeliveryTo.FEED);
</pre>

--
// Get alert by id.

<pre>
Alert alert = service.getAlertById(alertId);
</pre>

--
// Get alert by search query.

<pre>
List<Alert> lstAlert = service.getAlertsByQuery("Your Query");
</pre>

--
// Create alert. return an alert id if created successful else return an error string
// Default deliver is email

<pre>
Alert alert = new Alert();
alert.setHowMany(HowMany.ONLY_THE_BEST_RESULTS);
alert.setHowOften(HowOften.ONCE_A_DAY);
alert.setResultType(ResultType.EVERYTHING);
alert.setSearchQuery("Your Query");
alert.setDeliveryTo(DeliverTo.FEED);
String id = service.createAlert(alert);
</pre>

--
// Delete an alert.

<pre>
service.deleteAlert(alertId);
</pre>

--
// Delete list of alerts.

<pre>
List<String> lstAlertId = new ArrayList<String>();
lstAlertId.add(alertId);
service.deleteAlert(lstAlertId);
</pre>

--
// Update alert. return empty string if updated successful else return an error string

<pre>
AlertBean alert = new AlertBean();
alert.setId(editAlertId);
alert.setHowMany(HowMany.ONLY_THE_BEST_RESULTS);
alert.setHowOften(HowOften.ONCE_A_DAY);
alert.setSearchQuery("your new query");
alert.setDeliverTo(DeliverTo.FEED);
service.updateAlert(alert);
</pre>

--
Please contact me at nnhiti@gmail.com if you found any issues.

Happy coding.
