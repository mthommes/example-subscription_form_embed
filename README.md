ActiveCampaign Subscription Form API Script: Embed and customize your forms on any site.

## Requirements

1. [Our PHP API library](https://github.com/ActiveCampaign/activecampaign-api-php)
2. jQuery (if using the Ajax option, or loading existing contact details)

## Installation and Usage

You can install **example-subscription_form_embed** by downloading (or cloning) the source.

Input your ActiveCampaign URL and API Key. Example below:

<pre>
define("ACTIVECAMPAIGN_URL", "YOUR ACTIVECAMPAIGN URL");
define("ACTIVECAMPAIGN_API_KEY", "YOUR ACTIVECAMPAIGN API KEY");
</pre>

Make sure the path to the PHP library is correct:

<pre>
require_once("../../activecampaign-api-php/includes/ActiveCampaign.class.php");
</pre>

Set up your subscription form embed parameters:

<pre>
$form_embed_params = array(
  "id" => 1026,
  "action" => "",
  "ajax" => 1,
  "css" => 1,
);
</pre>

Here is a breakdown of each:

* `id`: The ID of your subscription form.
* `action`: The URL that your subscription form will post data to (leave out this parameter completely if you want to post it to the default location, or set to empty string to post to the same page the script is running).
* `ajax`: `0` or `1`. Whether or not the form submits via standard page reload, or Ajax (requires jQuery).
* `css`: `0` or `1`. Whether or not to include (or remove) the default CSS that comes with each subscription form.

Finally, decide whether to perform a sync or standard add/edit:

<pre>
// set to 1 to sync
$sync = 0;
</pre>

A sync does not require a subscriber ID, and will automatically add or edit, depending if they exist already (based on the email address). If you wish to simply perform an ADD (no edit), delete this portion of `Form.class.php`:

![Screenshot of code to remove EDIT portion](http://d226aj4ao1t61q.cloudfront.net/pitupi0v1_1.jpg)

To load an existing contact's details in your form (name, email, and custom field values), include the **contact hash** in the URL (IE: `index.php?hash=ihfsaduh038d3q...`).

![Screenshot of form filled with existing contact details](http://d226aj4ao1t61q.cloudfront.net/649ca2tr_screenshot2013-10-15at2.00.12pm.jpg)

[Learn more about syncing subscribers](http://www.activecampaign.com/blog/sync-subscribers-with-our-api/).

## Documentation and Links

* [Full API documentation](http://activecampaign.com/api)
* [Blog post: Advanced Subscription Form Integration](http://www.activecampaign.com/blog/advanced-subscription-form-integration/)

## Reporting Issues

We'd love to help if you have questions or problems. Report issues using the [Github Issue Tracker](https://github.com/ActiveCampaign/example-subscription_form_embed/issues) or email help@activecampaign.com.