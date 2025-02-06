<script src="%assets_url%/js/jquery371.js" type="text/javascript"></script>
<script src="%assets_url%/js/datatables.js" type="text/javascript"></script>
<script src="%assets_url%/js/jszip.js" type="text/javascript" defer></script>
<script src="%assets_url%/js/dataTables.buttons.js" type="text/javascript" defer></script>
<script src="%assets_url%/js/buttons.html5.js" type="text/javascript" defer></script>

<link href="%assets_url%/css/datatables.css" rel="stylesheet">

<center><a href="https://github.com/avoidthehack/Private-Browsers-Table" target="_blank"><img class="icons" src="%assets_url%//icons/github.svg" alt="github logo icon"> <a href="https://avoidthehack.com/contribute" target="_blank"><img class="icons" src="%assets_url%/icons/donate.svg" alt="hand with a heart icon"> <a href="https://avoidthehack.com/how-to-bct" target="_blank"><img class="icons" src="%assets_url%/icons/help.svg" alt="life raft help icon"></a></center>

<center><img src="%assets_url%/avoidthehack2.png" alt="avoidthehack logo"></center>

# Welcome to the Private Browser Comparison Tool

Use the Privacy Browser Comparison Tool to compare key points/features of different privacy browsers. This table is **interactive** and can be searched and locally exported to **Excel** or any spreadsheet software capable of working with `.xlsx` files.

**Note:** This tool requires JavaScript to run.

<script defer>
$(document).ready( function () {
    var table = $('#browsers').DataTable( {
        dom: 'Bfrtip',
        lengthMenu: [
            [5, 10, 15, 20, 30, -1],
            ['5 rows', '10 rows', '15 rows', '20 rows', '30 rows', 'Show all']
            ],
        buttons: [       
            'pageLength',               
             'copy',        
            {           
                extend: 'excel',            
                title: 'Privacy Browser Comparison',            
                messageTop: 'Use this information to choose your next Privacy Browser. Something missing or wrong? Contribute @ https://github.com/avoidthehack/Private-Browsers-Table',            
                messageBottom: 'Information in this document is pulled from various sources. If you see something missing and/or wrong, open an issue on the project GitHub repository.',        
            },        
        ],
        paging: true,
        "pageLength": 7,
        
        
        "ajax": "%assets_url%/json/browsers.json",
        "columns": [
            {
            "data": "more"
            },
            { "data": "logo",
            render: function (data, type, row, meta) {
                return '<img src="' + data + '" height="auto" width="80"/>';
              }
            },
            { "data": "browser" },
            { "data": "developer" },
            { "data": "engine" },
            { "data": "source" },
            { "data": "telemetry" },
            { "data": "track" },
            { "data": "script" },
            { "data": "fingerprint" },
            { "data": "webrtc" },
            { "data": "availability" },
            { "data": "sync" },
            { "data": "google" },
            { "data": "https" },
            { "data": "doh" },
            { "data": "extensions" },
            { "data": "search" }
        ],
        "order": [[1, 'asc']]
    } );
     
    } );
</script>

<table id="browsers" style="width:100%">
        <thead>
            <tr>
                <th>+</th>
                <th>Logo</th>
                <th>Browser</th>
                <th>Developer</th>
                <th>Engine</th>
                <th>Source code</th>
                <th>Telemetry</th>            
                <th>Tracker Blocking <sup><a href="https://avoidthehack.com/tools/tracker-blocking">
  <b>more info</b>
</a></sup></th>                 <th>Script blocking</th>            
                <th>Fingerprinting protection</th>            
                <th>Disable WebRTC <sup><a href="https://avoidthehack.com/webrtc-leaks-how-to-fix">
  <b>more info</b>
</a></sup></th>            
                <th>Availability</th>            
                <th>Sync</th>            
                <th>Google services?</th>            
                <th>Force HTTPS <sup><a href="https://avoidthehack.com/https-privacy">
  <b>more info</b>
</a></sup></th>            
                <th>DoH support</th>
                <th>Extension Compatibility</th>
                <th>Default Search <sup><a href="https://avoidthehack.com/best-private-search">
  <b>more info</b>
</a></sup></th>
            </tr>
        </thead>
    </table>

## Legend
dash (-) = N/A

**"must be enabled"** = feature is present, but not enabled by default

? = unknown/information missing (feel free to open an issue with the appropriate information)

_A [detailed how-to guide](https://avoidthehack.com/how-to-bct) for maximizing use of this table is available._


## Overview
Not all privacy browsers are built the same; as such they don't deliver the exact same results. However, many users may find that a private browser doesn't fulfill their goals for any reason. Most browser download pages focus on their own unique features when compared to the competition.

This tool aims to paint an as-complete-as-possible picture of the different privacy browsers out there before users commit to a download/install.

This privacy browser comparison tool aims to be easily readable and usable for all users, regardless of personal technical expertise.

**Note:** Browsers listed in this table are not specifically recommended by avoidthehack.com _unless_ indicated under the more information column ("avoidthehack" weigh-ins). The data in this table is provided as-is for warranty purposes.


<h2 id ="faq">FAQ</h2>

### Where can I view more information about the browsers listed here?
Under the "+" or "plus sign" column (the left most column), click the plus sign for the corresponding browser. Each "more information" page for each browser features a link to the browser's last known official website and/or download/repository pages.

If this information has changed, but isn't reflected here, then please open an issue on the [Private Browser Comparison Tool GitHub page](https://github.com/avoidthehack/Private-Browsers-Table/issues).

### Where can I download the browsers listed here?
1. Under the "+" column (left-most column in the table), click the plus sign for the corresponding browser.
2. Click the "Download" button on the browser's "Details" page.

### Where is Chrome, Edge, Safari?
Traditionally, these browsers aren't classified as "private" browsers. While they can be hardened to _some_ degree, it's generally recommended to migrate from these browsers when possible to do so. 

This is because the hardening process with these browsers can be tedious, requiring many different tweaks in different locations. Some settings may not be "Accessible" unless one is willing to edit code or go to more extreme measures. There is also the issue of silent automatic updates rolling back your changes to the new version's default.

If you're not familiar with the perils of using browsers like Microsoft and Google Chrome, then please get familiar with how these browsers are terrible for privacy @ the [avoidthehack Privacy Browsers page](https://avoidthehack.com/tools/privacy-browsers)

**Note:** Migrating from Safari on iOS is "limited" due to all third-party browsers on iOS forced to use WebKit (the same rendering engine as Safari). In some cases, it may be best to use Safari on iOS due to fingerprinting issues, while taking care to [tweak some settings](https://avoidthehack.com/configure-safari-privacy-ios).

### Where is TOR?
Since TOR is configured to run on the onion (Tor) network, this makes it a completely different animal from just about every browser found here. This isn't necessarily an overly "good" or "bad" thing - just that TOR is _different enough_ to not be included here.

TOR has many unique characteristics about and surrounding it, especially the technology behind the `.onion` network and its relay hops. TOR can be used to browse the clearnet, deepweb, and the "darknet."

TOR is generally recommended as the de facto standard for users looking to be **anonymous** while browsing. The browsers listed here may provide some privacy or security benefits, but generally do not provide anonymity.

More information on TOR:
* [Official TOR Project](https://www.torproject.org/)

### Where can I find recommended browsers?
When clicking the "+" or plus sign in the "+" (more information) column, some browsers may have a listed "recommended" status by avoidthehack. This means these browsers are recommended by avoidthehack.

For a curated list of recommended browsers, visit the [Privacy Browsers page](https://avoidthehack.com/tools/privacy-browsers) on avoidthehack.com

### Wait... what exactly is a privacy/privacy-oriented browser?

Privacy (or privacy-oriented browsers) respect the user's privacy and also take steps to help preserve the user's privacy when surfing the internet. Different privacy browsers implement different ways to accomplish both of these.

For more information, give "[What is a Privacy-Oriented Browser?](https://avoidthehack.com/what-is-a-privacy-focused-browser)" on avoidthehack.com a read.

### X browser is in alpha/beta, why isn't it listed?
Alpha or beta software is very volatile and often changes quickly. Additionally, many alpha and beta projects big and small are regularly abandoned. Browsers listed here are "mature enough" (typically version 1.0) and tend to not be as volatile.

### Where can I get a .csv file for this table?
As of July 2023, the previously hosted .csv file was deleted. Users are free to use the "copy" or "Export to Excel" buttons to create their own .csv file.

### How do I make a suggestion to this table/related pages?
The entirety of this subsite/tool is available on [GitHub](https://github.com/avoidthehack/Private-Browsers-Table). Feel free to open an issue there, but be sure to read the readme!
