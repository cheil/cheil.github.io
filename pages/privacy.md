---
title: Privacy Information
description: How this website handles your data
permalink: /privacy/
---

## Who runs this website

This website is run by Christoph Heil, Institute of Theoretical and Computational Physics, Graz University of Technology, Petersgasse 16, 8010 Graz, Austria. For any questions about your data, please write to [christoph.heil@tugraz.at](mailto:christoph.heil@tugraz.at).

## Hosting

The site is hosted on GitHub Pages, a service of GitHub, Inc. (USA). When you open a page, your browser sends technical data such as your IP address, the requested page and your browser type to GitHub's servers. GitHub needs this to deliver the page and keeps it in server logs for security purposes; see [GitHub's privacy statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement).

All fonts, icons and scripts of this site are served from GitHub Pages itself. No other external service is contacted, unless you agree to the usage statistics described below.

## Usage statistics (only with your consent)

On your first visit, a banner asks whether we may use Google Analytics. Only if you click *Approve* does the site load Google Analytics 4, a service of Google Ireland Limited (Ireland) and Google LLC (USA), which we use to count visits and to see which pages are read. Google Analytics sets cookies and processes data such as the pages you view, the time of your visit, your browser and device type, the website you came from, and your approximate location. This data may be transferred to and processed in the USA; Google LLC is certified under the EU-U.S. Data Privacy Framework. The legal basis is your consent (Art. 6(1)(a) GDPR). See [Google's privacy policy](https://policies.google.com/privacy).

If you click *Deny*, Google Analytics is not loaded and no usage data is collected. Your choice is stored in a cookie on your device for 31 days.

You can withdraw or change your choice at any time: <a href="#" id="reset-cookie-choice">reset your cookie choice</a> (the banner will appear again).

<script>
  document.getElementById('reset-cookie-choice').addEventListener('click', function (e) {
    e.preventDefault();
    var past = '=; expires=Thu, 01 Jan 1970 00:00:00 GMT; path=/';
    document.cookie.split(';').forEach(function (c) {
      var name = c.split('=')[0].trim();
      if (name === 'cookie-notice-option' || name.indexOf('_ga') === 0) {
        document.cookie = name + past;
        document.cookie = name + past + '; domain=' + location.hostname;
        document.cookie = name + past + '; domain=.' + location.hostname;
      }
    });
    location.reload();
  });
</script>

## Your rights

You have the right to access, rectification, erasure and restriction of processing of your data, to data portability and to object, and you can withdraw your consent at any time without affecting the lawfulness of processing before the withdrawal. If you believe that the processing of your data violates data protection law, you can lodge a complaint with the Austrian Data Protection Authority ([Datenschutzbehörde](https://www.dsb.gv.at)).
