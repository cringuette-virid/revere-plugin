# revere-plugin
## Revere General Installation Instructions

### Prepare Root Theme File

First step is to properly configure the root template to ensure basic configuration variables are available to every page. _If you are not working on a system which uses templates, ensure this markup is on every page of your site._

```
<script>
    var REV = {
        Base: '',               // this site's URL
        DataUrl: '',            // Revere Engine's URL
        CompandyId: '',         // company ID issued to you by Revere
        PageSize: 5,            // number of reviews per page - Default is 5
        TemplatePath: '',       // local path to your templates
        PostToFB: false,        // or true. whether or not reviews can be cross-posted to Facebook
        FBid: ''                // your company's Facebook ID
    }
</script>
```
Once you have created a variable named `REV` you must place the Revere engine on your page. To do so, place the following script tag on your root template page:

```
<link href="[path]/[to]/[local]/revere.min.css" rel="stylesheet">
<script src="[path]/[to]/[local]/revere.min.js"></script>
```

Ideally, the `<link>` tag would be in the `<head>` of the document, and the `<script>` tag would be as close to the bottom near the closing `</body>` tag as possible. This will ensure higher Google PageSpeed rankings. However, placing them both towards the bottom of the page will suffice.

#### Cross-post Reviews to Facebook
If you would like to enable Facebook cross-posting functionality set the `PostToFB` flag to `true` and ensure you have entered in a valid `FBid`, both are found in the `REV` variable object. Once you have ensured proper `REV` object configuration, place the following snippet as close to the opening `<body>` element on the root template as possible.

```
<div id="fb-root"></div>
<script>
    // Load the SDK's source Asynchronously
    (function (d, s, id) {
        var js, fjs = d.getElementsByTagName(s)[0];
        if (d.getElementById(id)) return;
        js = d.createElement(s); js.id = id;
        js.src = "//connect.facebook.net/en_US/sdk.js";
        fjs.parentNode.insertBefore(js, fjs);
    }(document, 'script', 'facebook-jssdk'));
</script>
```
#### Done with Step 1!
That's it for the root template! Revere's core engine is now installed and ready to for use across your site. Continue through the setup instructions to learn how to activate Revere's various features!

### Prepare Product Display Pages
On product detail/product display pages, you will often want to display not only the reviews but a likes snippet

### Add Snippets to Listing Pages

### Attach Cart Object for Purchase Tracking
