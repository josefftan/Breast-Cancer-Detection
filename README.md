<html>
<head><meta charset="utf-8">

<title>Breast Cancer Detection</title>

<script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.0.3/jquery.min.js"></script>



<style type="text/css">
    /*!
*
* Twitter Bootstrap
*
*/
/*!
 * Bootstrap v3.3.7 (http://getbootstrap.com)
 * Copyright 2011-2016 Twitter, Inc.
 * Licensed under MIT (https://github.com/twbs/bootstrap/blob/master/LICENSE)
 */
/*! normalize.css v3.0.3 | MIT License | github.com/necolas/normalize.css */
html {
  font-family: sans-serif;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
}
body {
  margin: 0;
}
article,
aside,
details,
figcaption,
figure,
footer,
header,
hgroup,
main,
menu,
nav,
section,
summary {
  display: block;
}
audio,
canvas,
progress,
video {
  display: inline-block;
  vertical-align: baseline;
}
audio:not([controls]) {
  display: none;
  height: 0;
}
[hidden],
template {
  display: none;
}
a {
  background-color: transparent;
}
a:active,
a:hover {
  outline: 0;
}
abbr[title] {
  border-bottom: 1px dotted;
}
b,
strong {
  font-weight: bold;
}
dfn {
  font-style: italic;
}
h1 {
  font-size: 2em;
  margin: 0.67em 0;
}
mark {
  background: #ff0;
  color: #000;
}
small {
  font-size: 80%;
}
sub,
sup {
  font-size: 75%;
  line-height: 0;
  position: relative;
  vertical-align: baseline;
}
sup {
  top: -0.5em;
}
sub {
  bottom: -0.25em;
}
img {
  border: 0;
}
svg:not(:root) {
  overflow: hidden;
}
figure {
  margin: 1em 40px;
}
hr {
  box-sizing: content-box;
  height: 0;
}
pre {
  overflow: auto;
}
code,
kbd,
pre,
samp {
  font-family: monospace, monospace;
  font-size: 1em;
}
button,
input,
optgroup,
select,
textarea {
  color: inherit;
  font: inherit;
  margin: 0;
}
button {
  overflow: visible;
}
button,
select {
  text-transform: none;
}
button,
html input[type="button"],
input[type="reset"],
input[type="submit"] {
  -webkit-appearance: button;
  cursor: pointer;
}
button[disabled],
html input[disabled] {
  cursor: default;
}
button::-moz-focus-inner,
input::-moz-focus-inner {
  border: 0;
  padding: 0;
}
input {
  line-height: normal;
}
input[type="checkbox"],
input[type="radio"] {
  box-sizing: border-box;
  padding: 0;
}
input[type="number"]::-webkit-inner-spin-button,
input[type="number"]::-webkit-outer-spin-button {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: textfield;
  box-sizing: content-box;
}
input[type="search"]::-webkit-search-cancel-button,
input[type="search"]::-webkit-search-decoration {
  -webkit-appearance: none;
}
fieldset {
  border: 1px solid #c0c0c0;
  margin: 0 2px;
  padding: 0.35em 0.625em 0.75em;
}
legend {
  border: 0;
  padding: 0;
}
textarea {
  overflow: auto;
}
optgroup {
  font-weight: bold;
}
table {
  border-collapse: collapse;
  border-spacing: 0;
}
td,
th {
  padding: 0;
}
/*! Source: https://github.com/h5bp/html5-boilerplate/blob/master/src/css/main.css */
@media print {
  *,
  *:before,
  *:after {
    background: transparent !important;
    box-shadow: none !important;
    text-shadow: none !important;
  }
  a,
  a:visited {
    text-decoration: underline;
  }
  a[href]:after {
    content: " (" attr(href) ")";
  }
  abbr[title]:after {
    content: " (" attr(title) ")";
  }
  a[href^="#"]:after,
  a[href^="javascript:"]:after {
    content: "";
  }
  pre,
  blockquote {
    border: 1px solid #999;
    page-break-inside: avoid;
  }
  thead {
    display: table-header-group;
  }
  tr,
  img {
    page-break-inside: avoid;
  }
  img {
    max-width: 100% !important;
  }
  p,
  h2,
  h3 {
    orphans: 3;
    widows: 3;
  }
  h2,
  h3 {
    page-break-after: avoid;
  }
  .navbar {
    display: none;
  }
  .btn > .caret,
  .dropup > .btn > .caret {
    border-top-color: #000 !important;
  }
  .label {
    border: 1px solid #000;
  }
  .table {
    border-collapse: collapse !important;
  }
  .table td,
  .table th {
    background-color: #fff !important;
  }
  .table-bordered th,
  .table-bordered td {
    border: 1px solid #ddd !important;
  }
}
@font-face {
  font-family: 'Glyphicons Halflings';
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot');
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot?#iefix') format('embedded-opentype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff2') format('woff2'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff') format('woff'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.ttf') format('truetype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.svg#glyphicons_halflingsregular') format('svg');
}
.glyphicon {
  position: relative;
  top: 1px;
  display: inline-block;
  font-family: 'Glyphicons Halflings';
  font-style: normal;
  font-weight: normal;
  line-height: 1;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.glyphicon-asterisk:before {
  content: "\002a";
}
.glyphicon-plus:before {
  content: "\002b";
}
.glyphicon-euro:before,
.glyphicon-eur:before {
  content: "\20ac";
}
.glyphicon-minus:before {
  content: "\2212";
}
.glyphicon-cloud:before {
  content: "\2601";
}
.glyphicon-envelope:before {
  content: "\2709";
}
.glyphicon-pencil:before {
  content: "\270f";
}
.glyphicon-glass:before {
  content: "\e001";
}
.glyphicon-music:before {
  content: "\e002";
}
.glyphicon-search:before {
  content: "\e003";
}
.glyphicon-heart:before {
  content: "\e005";
}
.glyphicon-star:before {
  content: "\e006";
}
.glyphicon-star-empty:before {
  content: "\e007";
}
.glyphicon-user:before {
  content: "\e008";
}
.glyphicon-film:before {
  content: "\e009";
}
.glyphicon-th-large:before {
  content: "\e010";
}
.glyphicon-th:before {
  content: "\e011";
}
.glyphicon-th-list:before {
  content: "\e012";
}
.glyphicon-ok:before {
  content: "\e013";
}
.glyphicon-remove:before {
  content: "\e014";
}
.glyphicon-zoom-in:before {
  content: "\e015";
}
.glyphicon-zoom-out:before {
  content: "\e016";
}
.glyphicon-off:before {
  content: "\e017";
}
.glyphicon-signal:before {
  content: "\e018";
}
.glyphicon-cog:before {
  content: "\e019";
}
.glyphicon-trash:before {
  content: "\e020";
}
.glyphicon-home:before {
  content: "\e021";
}
.glyphicon-file:before {
  content: "\e022";
}
.glyphicon-time:before {
  content: "\e023";
}
.glyphicon-road:before {
  content: "\e024";
}
.glyphicon-download-alt:before {
  content: "\e025";
}
.glyphicon-download:before {
  content: "\e026";
}
.glyphicon-upload:before {
  content: "\e027";
}
.glyphicon-inbox:before {
  content: "\e028";
}
.glyphicon-play-circle:before {
  content: "\e029";
}
.glyphicon-repeat:before {
  content: "\e030";
}
.glyphicon-refresh:before {
  content: "\e031";
}
.glyphicon-list-alt:before {
  content: "\e032";
}
.glyphicon-lock:before {
  content: "\e033";
}
.glyphicon-flag:before {
  content: "\e034";
}
.glyphicon-headphones:before {
  content: "\e035";
}
.glyphicon-volume-off:before {
  content: "\e036";
}
.glyphicon-volume-down:before {
  content: "\e037";
}
.glyphicon-volume-up:before {
  content: "\e038";
}
.glyphicon-qrcode:before {
  content: "\e039";
}
.glyphicon-barcode:before {
  content: "\e040";
}
.glyphicon-tag:before {
  content: "\e041";
}
.glyphicon-tags:before {
  content: "\e042";
}
.glyphicon-book:before {
  content: "\e043";
}
.glyphicon-bookmark:before {
  content: "\e044";
}
.glyphicon-print:before {
  content: "\e045";
}
.glyphicon-camera:before {
  content: "\e046";
}
.glyphicon-font:before {
  content: "\e047";
}
.glyphicon-bold:before {
  content: "\e048";
}
.glyphicon-italic:before {
  content: "\e049";
}
.glyphicon-text-height:before {
  content: "\e050";
}
.glyphicon-text-width:before {
  content: "\e051";
}
.glyphicon-align-left:before {
  content: "\e052";
}
.glyphicon-align-center:before {
  content: "\e053";
}
.glyphicon-align-right:before {
  content: "\e054";
}
.glyphicon-align-justify:before {
  content: "\e055";
}
.glyphicon-list:before {
  content: "\e056";
}
.glyphicon-indent-left:before {
  content: "\e057";
}
.glyphicon-indent-right:before {
  content: "\e058";
}
.glyphicon-facetime-video:before {
  content: "\e059";
}
.glyphicon-picture:before {
  content: "\e060";
}
.glyphicon-map-marker:before {
  content: "\e062";
}
.glyphicon-adjust:before {
  content: "\e063";
}
.glyphicon-tint:before {
  content: "\e064";
}
.glyphicon-edit:before {
  content: "\e065";
}
.glyphicon-share:before {
  content: "\e066";
}
.glyphicon-check:before {
  content: "\e067";
}
.glyphicon-move:before {
  content: "\e068";
}
.glyphicon-step-backward:before {
  content: "\e069";
}
.glyphicon-fast-backward:before {
  content: "\e070";
}
.glyphicon-backward:before {
  content: "\e071";
}
.glyphicon-play:before {
  content: "\e072";
}
.glyphicon-pause:before {
  content: "\e073";
}
.glyphicon-stop:before {
  content: "\e074";
}
.glyphicon-forward:before {
  content: "\e075";
}
.glyphicon-fast-forward:before {
  content: "\e076";
}
.glyphicon-step-forward:before {
  content: "\e077";
}
.glyphicon-eject:before {
  content: "\e078";
}
.glyphicon-chevron-left:before {
  content: "\e079";
}
.glyphicon-chevron-right:before {
  content: "\e080";
}
.glyphicon-plus-sign:before {
  content: "\e081";
}
.glyphicon-minus-sign:before {
  content: "\e082";
}
.glyphicon-remove-sign:before {
  content: "\e083";
}
.glyphicon-ok-sign:before {
  content: "\e084";
}
.glyphicon-question-sign:before {
  content: "\e085";
}
.glyphicon-info-sign:before {
  content: "\e086";
}
.glyphicon-screenshot:before {
  content: "\e087";
}
.glyphicon-remove-circle:before {
  content: "\e088";
}
.glyphicon-ok-circle:before {
  content: "\e089";
}
.glyphicon-ban-circle:before {
  content: "\e090";
}
.glyphicon-arrow-left:before {
  content: "\e091";
}
.glyphicon-arrow-right:before {
  content: "\e092";
}
.glyphicon-arrow-up:before {
  content: "\e093";
}
.glyphicon-arrow-down:before {
  content: "\e094";
}
.glyphicon-share-alt:before {
  content: "\e095";
}
.glyphicon-resize-full:before {
  content: "\e096";
}
.glyphicon-resize-small:before {
  content: "\e097";
}
.glyphicon-exclamation-sign:before {
  content: "\e101";
}
.glyphicon-gift:before {
  content: "\e102";
}
.glyphicon-leaf:before {
  content: "\e103";
}
.glyphicon-fire:before {
  content: "\e104";
}
.glyphicon-eye-open:before {
  content: "\e105";
}
.glyphicon-eye-close:before {
  content: "\e106";
}
.glyphicon-warning-sign:before {
  content: "\e107";
}
.glyphicon-plane:before {
  content: "\e108";
}
.glyphicon-calendar:before {
  content: "\e109";
}
.glyphicon-random:before {
  content: "\e110";
}
.glyphicon-comment:before {
  content: "\e111";
}
.glyphicon-magnet:before {
  content: "\e112";
}
.glyphicon-chevron-up:before {
  content: "\e113";
}
.glyphicon-chevron-down:before {
  content: "\e114";
}
.glyphicon-retweet:before {
  content: "\e115";
}
.glyphicon-shopping-cart:before {
  content: "\e116";
}
.glyphicon-folder-close:before {
  content: "\e117";
}
.glyphicon-folder-open:before {
  content: "\e118";
}
.glyphicon-resize-vertical:before {
  content: "\e119";
}
.glyphicon-resize-horizontal:before {
  content: "\e120";
}
.glyphicon-hdd:before {
  content: "\e121";
}
.glyphicon-bullhorn:before {
  content: "\e122";
}
.glyphicon-bell:before {
  content: "\e123";
}
.glyphicon-certificate:before {
  content: "\e124";
}
.glyphicon-thumbs-up:before {
  content: "\e125";
}
.glyphicon-thumbs-down:before {
  content: "\e126";
}
.glyphicon-hand-right:before {
  content: "\e127";
}
.glyphicon-hand-left:before {
  content: "\e128";
}
.glyphicon-hand-up:before {
  content: "\e129";
}
.glyphicon-hand-down:before {
  content: "\e130";
}
.glyphicon-circle-arrow-right:before {
  content: "\e131";
}
.glyphicon-circle-arrow-left:before {
  content: "\e132";
}
.glyphicon-circle-arrow-up:before {
  content: "\e133";
}
.glyphicon-circle-arrow-down:before {
  content: "\e134";
}
.glyphicon-globe:before {
  content: "\e135";
}
.glyphicon-wrench:before {
  content: "\e136";
}
.glyphicon-tasks:before {
  content: "\e137";
}
.glyphicon-filter:before {
  content: "\e138";
}
.glyphicon-briefcase:before {
  content: "\e139";
}
.glyphicon-fullscreen:before {
  content: "\e140";
}
.glyphicon-dashboard:before {
  content: "\e141";
}
.glyphicon-paperclip:before {
  content: "\e142";
}
.glyphicon-heart-empty:before {
  content: "\e143";
}
.glyphicon-link:before {
  content: "\e144";
}
.glyphicon-phone:before {
  content: "\e145";
}
.glyphicon-pushpin:before {
  content: "\e146";
}
.glyphicon-usd:before {
  content: "\e148";
}
.glyphicon-gbp:before {
  content: "\e149";
}
.glyphicon-sort:before {
  content: "\e150";
}
.glyphicon-sort-by-alphabet:before {
  content: "\e151";
}
.glyphicon-sort-by-alphabet-alt:before {
  content: "\e152";
}
.glyphicon-sort-by-order:before {
  content: "\e153";
}
.glyphicon-sort-by-order-alt:before {
  content: "\e154";
}
.glyphicon-sort-by-attributes:before {
  content: "\e155";
}
.glyphicon-sort-by-attributes-alt:before {
  content: "\e156";
}
.glyphicon-unchecked:before {
  content: "\e157";
}
.glyphicon-expand:before {
  content: "\e158";
}
.glyphicon-collapse-down:before {
  content: "\e159";
}
.glyphicon-collapse-up:before {
  content: "\e160";
}
.glyphicon-log-in:before {
  content: "\e161";
}
.glyphicon-flash:before {
  content: "\e162";
}
.glyphicon-log-out:before {
  content: "\e163";
}
.glyphicon-new-window:before {
  content: "\e164";
}
.glyphicon-record:before {
  content: "\e165";
}
.glyphicon-save:before {
  content: "\e166";
}
.glyphicon-open:before {
  content: "\e167";
}
.glyphicon-saved:before {
  content: "\e168";
}
.glyphicon-import:before {
  content: "\e169";
}
.glyphicon-export:before {
  content: "\e170";
}
.glyphicon-send:before {
  content: "\e171";
}
.glyphicon-floppy-disk:before {
  content: "\e172";
}
.glyphicon-floppy-saved:before {
  content: "\e173";
}
.glyphicon-floppy-remove:before {
  content: "\e174";
}
.glyphicon-floppy-save:before {
  content: "\e175";
}
.glyphicon-floppy-open:before {
  content: "\e176";
}
.glyphicon-credit-card:before {
  content: "\e177";
}
.glyphicon-transfer:before {
  content: "\e178";
}
.glyphicon-cutlery:before {
  content: "\e179";
}
.glyphicon-header:before {
  content: "\e180";
}
.glyphicon-compressed:before {
  content: "\e181";
}
.glyphicon-earphone:before {
  content: "\e182";
}
.glyphicon-phone-alt:before {
  content: "\e183";
}
.glyphicon-tower:before {
  content: "\e184";
}
.glyphicon-stats:before {
  content: "\e185";
}
.glyphicon-sd-video:before {
  content: "\e186";
}
.glyphicon-hd-video:before {
  content: "\e187";
}
.glyphicon-subtitles:before {
  content: "\e188";
}
.glyphicon-sound-stereo:before {
  content: "\e189";
}
.glyphicon-sound-dolby:before {
  content: "\e190";
}
.glyphicon-sound-5-1:before {
  content: "\e191";
}
.glyphicon-sound-6-1:before {
  content: "\e192";
}
.glyphicon-sound-7-1:before {
  content: "\e193";
}
.glyphicon-copyright-mark:before {
  content: "\e194";
}
.glyphicon-registration-mark:before {
  content: "\e195";
}
.glyphicon-cloud-download:before {
  content: "\e197";
}
.glyphicon-cloud-upload:before {
  content: "\e198";
}
.glyphicon-tree-conifer:before {
  content: "\e199";
}
.glyphicon-tree-deciduous:before {
  content: "\e200";
}
.glyphicon-cd:before {
  content: "\e201";
}
.glyphicon-save-file:before {
  content: "\e202";
}
.glyphicon-open-file:before {
  content: "\e203";
}
.glyphicon-level-up:before {
  content: "\e204";
}
.glyphicon-copy:before {
  content: "\e205";
}
.glyphicon-paste:before {
  content: "\e206";
}
.glyphicon-alert:before {
  content: "\e209";
}
.glyphicon-equalizer:before {
  content: "\e210";
}
.glyphicon-king:before {
  content: "\e211";
}
.glyphicon-queen:before {
  content: "\e212";
}
.glyphicon-pawn:before {
  content: "\e213";
}
.glyphicon-bishop:before {
  content: "\e214";
}
.glyphicon-knight:before {
  content: "\e215";
}
.glyphicon-baby-formula:before {
  content: "\e216";
}
.glyphicon-tent:before {
  content: "\26fa";
}
.glyphicon-blackboard:before {
  content: "\e218";
}
.glyphicon-bed:before {
  content: "\e219";
}
.glyphicon-apple:before {
  content: "\f8ff";
}
.glyphicon-erase:before {
  content: "\e221";
}
.glyphicon-hourglass:before {
  content: "\231b";
}
.glyphicon-lamp:before {
  content: "\e223";
}
.glyphicon-duplicate:before {
  content: "\e224";
}
.glyphicon-piggy-bank:before {
  content: "\e225";
}
.glyphicon-scissors:before {
  content: "\e226";
}
.glyphicon-bitcoin:before {
  content: "\e227";
}
.glyphicon-btc:before {
  content: "\e227";
}
.glyphicon-xbt:before {
  content: "\e227";
}
.glyphicon-yen:before {
  content: "\00a5";
}
.glyphicon-jpy:before {
  content: "\00a5";
}
.glyphicon-ruble:before {
  content: "\20bd";
}
.glyphicon-rub:before {
  content: "\20bd";
}
.glyphicon-scale:before {
  content: "\e230";
}
.glyphicon-ice-lolly:before {
  content: "\e231";
}
.glyphicon-ice-lolly-tasted:before {
  content: "\e232";
}
.glyphicon-education:before {
  content: "\e233";
}
.glyphicon-option-horizontal:before {
  content: "\e234";
}
.glyphicon-option-vertical:before {
  content: "\e235";
}
.glyphicon-menu-hamburger:before {
  content: "\e236";
}
.glyphicon-modal-window:before {
  content: "\e237";
}
.glyphicon-oil:before {
  content: "\e238";
}
.glyphicon-grain:before {
  content: "\e239";
}
.glyphicon-sunglasses:before {
  content: "\e240";
}
.glyphicon-text-size:before {
  content: "\e241";
}
.glyphicon-text-color:before {
  content: "\e242";
}
.glyphicon-text-background:before {
  content: "\e243";
}
.glyphicon-object-align-top:before {
  content: "\e244";
}
.glyphicon-object-align-bottom:before {
  content: "\e245";
}
.glyphicon-object-align-horizontal:before {
  content: "\e246";
}
.glyphicon-object-align-left:before {
  content: "\e247";
}
.glyphicon-object-align-vertical:before {
  content: "\e248";
}
.glyphicon-object-align-right:before {
  content: "\e249";
}
.glyphicon-triangle-right:before {
  content: "\e250";
}
.glyphicon-triangle-left:before {
  content: "\e251";
}
.glyphicon-triangle-bottom:before {
  content: "\e252";
}
.glyphicon-triangle-top:before {
  content: "\e253";
}
.glyphicon-console:before {
  content: "\e254";
}
.glyphicon-superscript:before {
  content: "\e255";
}
.glyphicon-subscript:before {
  content: "\e256";
}
.glyphicon-menu-left:before {
  content: "\e257";
}
.glyphicon-menu-right:before {
  content: "\e258";
}
.glyphicon-menu-down:before {
  content: "\e259";
}
.glyphicon-menu-up:before {
  content: "\e260";
}
* {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
*:before,
*:after {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
html {
  font-size: 10px;
  -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
}
body {
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-size: 13px;
  line-height: 1.42857143;
  color: #000;
  background-color: #fff;
}
input,
button,
select,
textarea {
  font-family: inherit;
  font-size: inherit;
  line-height: inherit;
}
a {
  color: #337ab7;
  text-decoration: none;
}
a:hover,
a:focus {
  color: #23527c;
  text-decoration: underline;
}
a:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
figure {
  margin: 0;
}
img {
  vertical-align: middle;
}
.img-responsive,
.thumbnail > img,
.thumbnail a > img,
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  display: block;
  max-width: 100%;
  height: auto;
}
.img-rounded {
  border-radius: 3px;
}
.img-thumbnail {
  padding: 4px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: all 0.2s ease-in-out;
  -o-transition: all 0.2s ease-in-out;
  transition: all 0.2s ease-in-out;
  display: inline-block;
  max-width: 100%;
  height: auto;
}
.img-circle {
  border-radius: 50%;
}
hr {
  margin-top: 18px;
  margin-bottom: 18px;
  border: 0;
  border-top: 1px solid #eeeeee;
}
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: -1px;
  padding: 0;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
[role="button"] {
  cursor: pointer;
}
h1,
h2,
h3,
h4,
h5,
h6,
.h1,
.h2,
.h3,
.h4,
.h5,
.h6 {
  font-family: inherit;
  font-weight: 500;
  line-height: 1.1;
  color: inherit;
}
h1 small,
h2 small,
h3 small,
h4 small,
h5 small,
h6 small,
.h1 small,
.h2 small,
.h3 small,
.h4 small,
.h5 small,
.h6 small,
h1 .small,
h2 .small,
h3 .small,
h4 .small,
h5 .small,
h6 .small,
.h1 .small,
.h2 .small,
.h3 .small,
.h4 .small,
.h5 .small,
.h6 .small {
  font-weight: normal;
  line-height: 1;
  color: #777777;
}
h1,
.h1,
h2,
.h2,
h3,
.h3 {
  margin-top: 18px;
  margin-bottom: 9px;
}
h1 small,
.h1 small,
h2 small,
.h2 small,
h3 small,
.h3 small,
h1 .small,
.h1 .small,
h2 .small,
.h2 .small,
h3 .small,
.h3 .small {
  font-size: 65%;
}
h4,
.h4,
h5,
.h5,
h6,
.h6 {
  margin-top: 9px;
  margin-bottom: 9px;
}
h4 small,
.h4 small,
h5 small,
.h5 small,
h6 small,
.h6 small,
h4 .small,
.h4 .small,
h5 .small,
.h5 .small,
h6 .small,
.h6 .small {
  font-size: 75%;
}
h1,
.h1 {
  font-size: 33px;
}
h2,
.h2 {
  font-size: 27px;
}
h3,
.h3 {
  font-size: 23px;
}
h4,
.h4 {
  font-size: 17px;
}
h5,
.h5 {
  font-size: 13px;
}
h6,
.h6 {
  font-size: 12px;
}
p {
  margin: 0 0 9px;
}
.lead {
  margin-bottom: 18px;
  font-size: 14px;
  font-weight: 300;
  line-height: 1.4;
}
@media (min-width: 768px) {
  .lead {
    font-size: 19.5px;
  }
}
small,
.small {
  font-size: 92%;
}
mark,
.mark {
  background-color: #fcf8e3;
  padding: .2em;
}
.text-left {
  text-align: left;
}
.text-right {
  text-align: right;
}
.text-center {
  text-align: center;
}
.text-justify {
  text-align: justify;
}
.text-nowrap {
  white-space: nowrap;
}
.text-lowercase {
  text-transform: lowercase;
}
.text-uppercase {
  text-transform: uppercase;
}
.text-capitalize {
  text-transform: capitalize;
}
.text-muted {
  color: #777777;
}
.text-primary {
  color: #337ab7;
}
a.text-primary:hover,
a.text-primary:focus {
  color: #286090;
}
.text-success {
  color: #3c763d;
}
a.text-success:hover,
a.text-success:focus {
  color: #2b542c;
}
.text-info {
  color: #31708f;
}
a.text-info:hover,
a.text-info:focus {
  color: #245269;
}
.text-warning {
  color: #8a6d3b;
}
a.text-warning:hover,
a.text-warning:focus {
  color: #66512c;
}
.text-danger {
  color: #a94442;
}
a.text-danger:hover,
a.text-danger:focus {
  color: #843534;
}
.bg-primary {
  color: #fff;
  background-color: #337ab7;
}
a.bg-primary:hover,
a.bg-primary:focus {
  background-color: #286090;
}
.bg-success {
  background-color: #dff0d8;
}
a.bg-success:hover,
a.bg-success:focus {
  background-color: #c1e2b3;
}
.bg-info {
  background-color: #d9edf7;
}
a.bg-info:hover,
a.bg-info:focus {
  background-color: #afd9ee;
}
.bg-warning {
  background-color: #fcf8e3;
}
a.bg-warning:hover,
a.bg-warning:focus {
  background-color: #f7ecb5;
}
.bg-danger {
  background-color: #f2dede;
}
a.bg-danger:hover,
a.bg-danger:focus {
  background-color: #e4b9b9;
}
.page-header {
  padding-bottom: 8px;
  margin: 36px 0 18px;
  border-bottom: 1px solid #eeeeee;
}
ul,
ol {
  margin-top: 0;
  margin-bottom: 9px;
}
ul ul,
ol ul,
ul ol,
ol ol {
  margin-bottom: 0;
}
.list-unstyled {
  padding-left: 0;
  list-style: none;
}
.list-inline {
  padding-left: 0;
  list-style: none;
  margin-left: -5px;
}
.list-inline > li {
  display: inline-block;
  padding-left: 5px;
  padding-right: 5px;
}
dl {
  margin-top: 0;
  margin-bottom: 18px;
}
dt,
dd {
  line-height: 1.42857143;
}
dt {
  font-weight: bold;
}
dd {
  margin-left: 0;
}
@media (min-width: 541px) {
  .dl-horizontal dt {
    float: left;
    width: 160px;
    clear: left;
    text-align: right;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }
  .dl-horizontal dd {
    margin-left: 180px;
  }
}
abbr[title],
abbr[data-original-title] {
  cursor: help;
  border-bottom: 1px dotted #777777;
}
.initialism {
  font-size: 90%;
  text-transform: uppercase;
}
blockquote {
  padding: 9px 18px;
  margin: 0 0 18px;
  font-size: inherit;
  border-left: 5px solid #eeeeee;
}
blockquote p:last-child,
blockquote ul:last-child,
blockquote ol:last-child {
  margin-bottom: 0;
}
blockquote footer,
blockquote small,
blockquote .small {
  display: block;
  font-size: 80%;
  line-height: 1.42857143;
  color: #777777;
}
blockquote footer:before,
blockquote small:before,
blockquote .small:before {
  content: '\2014 \00A0';
}
.blockquote-reverse,
blockquote.pull-right {
  padding-right: 15px;
  padding-left: 0;
  border-right: 5px solid #eeeeee;
  border-left: 0;
  text-align: right;
}
.blockquote-reverse footer:before,
blockquote.pull-right footer:before,
.blockquote-reverse small:before,
blockquote.pull-right small:before,
.blockquote-reverse .small:before,
blockquote.pull-right .small:before {
  content: '';
}
.blockquote-reverse footer:after,
blockquote.pull-right footer:after,
.blockquote-reverse small:after,
blockquote.pull-right small:after,
.blockquote-reverse .small:after,
blockquote.pull-right .small:after {
  content: '\00A0 \2014';
}
address {
  margin-bottom: 18px;
  font-style: normal;
  line-height: 1.42857143;
}
code,
kbd,
pre,
samp {
  font-family: monospace;
}
code {
  padding: 2px 4px;
  font-size: 90%;
  color: #c7254e;
  background-color: #f9f2f4;
  border-radius: 2px;
}
kbd {
  padding: 2px 4px;
  font-size: 90%;
  color: #888;
  background-color: transparent;
  border-radius: 1px;
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.25);
}
kbd kbd {
  padding: 0;
  font-size: 100%;
  font-weight: bold;
  box-shadow: none;
}
pre {
  display: block;
  padding: 8.5px;
  margin: 0 0 9px;
  font-size: 12px;
  line-height: 1.42857143;
  word-break: break-all;
  word-wrap: break-word;
  color: #333333;
  background-color: #f5f5f5;
  border: 1px solid #ccc;
  border-radius: 2px;
}
pre code {
  padding: 0;
  font-size: inherit;
  color: inherit;
  white-space: pre-wrap;
  background-color: transparent;
  border-radius: 0;
}
.pre-scrollable {
  max-height: 340px;
  overflow-y: scroll;
}
.container {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
@media (min-width: 768px) {
  .container {
    width: 768px;
  }
}
@media (min-width: 992px) {
  .container {
    width: 940px;
  }
}
@media (min-width: 1200px) {
  .container {
    width: 1140px;
  }
}
.container-fluid {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
.row {
  margin-left: 0px;
  margin-right: 0px;
}
.col-xs-1, .col-sm-1, .col-md-1, .col-lg-1, .col-xs-2, .col-sm-2, .col-md-2, .col-lg-2, .col-xs-3, .col-sm-3, .col-md-3, .col-lg-3, .col-xs-4, .col-sm-4, .col-md-4, .col-lg-4, .col-xs-5, .col-sm-5, .col-md-5, .col-lg-5, .col-xs-6, .col-sm-6, .col-md-6, .col-lg-6, .col-xs-7, .col-sm-7, .col-md-7, .col-lg-7, .col-xs-8, .col-sm-8, .col-md-8, .col-lg-8, .col-xs-9, .col-sm-9, .col-md-9, .col-lg-9, .col-xs-10, .col-sm-10, .col-md-10, .col-lg-10, .col-xs-11, .col-sm-11, .col-md-11, .col-lg-11, .col-xs-12, .col-sm-12, .col-md-12, .col-lg-12 {
  position: relative;
  min-height: 1px;
  padding-left: 0px;
  padding-right: 0px;
}
.col-xs-1, .col-xs-2, .col-xs-3, .col-xs-4, .col-xs-5, .col-xs-6, .col-xs-7, .col-xs-8, .col-xs-9, .col-xs-10, .col-xs-11, .col-xs-12 {
  float: left;
}
.col-xs-12 {
  width: 100%;
}
.col-xs-11 {
  width: 91.66666667%;
}
.col-xs-10 {
  width: 83.33333333%;
}
.col-xs-9 {
  width: 75%;
}
.col-xs-8 {
  width: 66.66666667%;
}
.col-xs-7 {
  width: 58.33333333%;
}
.col-xs-6 {
  width: 50%;
}
.col-xs-5 {
  width: 41.66666667%;
}
.col-xs-4 {
  width: 33.33333333%;
}
.col-xs-3 {
  width: 25%;
}
.col-xs-2 {
  width: 16.66666667%;
}
.col-xs-1 {
  width: 8.33333333%;
}
.col-xs-pull-12 {
  right: 100%;
}
.col-xs-pull-11 {
  right: 91.66666667%;
}
.col-xs-pull-10 {
  right: 83.33333333%;
}
.col-xs-pull-9 {
  right: 75%;
}
.col-xs-pull-8 {
  right: 66.66666667%;
}
.col-xs-pull-7 {
  right: 58.33333333%;
}
.col-xs-pull-6 {
  right: 50%;
}
.col-xs-pull-5 {
  right: 41.66666667%;
}
.col-xs-pull-4 {
  right: 33.33333333%;
}
.col-xs-pull-3 {
  right: 25%;
}
.col-xs-pull-2 {
  right: 16.66666667%;
}
.col-xs-pull-1 {
  right: 8.33333333%;
}
.col-xs-pull-0 {
  right: auto;
}
.col-xs-push-12 {
  left: 100%;
}
.col-xs-push-11 {
  left: 91.66666667%;
}
.col-xs-push-10 {
  left: 83.33333333%;
}
.col-xs-push-9 {
  left: 75%;
}
.col-xs-push-8 {
  left: 66.66666667%;
}
.col-xs-push-7 {
  left: 58.33333333%;
}
.col-xs-push-6 {
  left: 50%;
}
.col-xs-push-5 {
  left: 41.66666667%;
}
.col-xs-push-4 {
  left: 33.33333333%;
}
.col-xs-push-3 {
  left: 25%;
}
.col-xs-push-2 {
  left: 16.66666667%;
}
.col-xs-push-1 {
  left: 8.33333333%;
}
.col-xs-push-0 {
  left: auto;
}
.col-xs-offset-12 {
  margin-left: 100%;
}
.col-xs-offset-11 {
  margin-left: 91.66666667%;
}
.col-xs-offset-10 {
  margin-left: 83.33333333%;
}
.col-xs-offset-9 {
  margin-left: 75%;
}
.col-xs-offset-8 {
  margin-left: 66.66666667%;
}
.col-xs-offset-7 {
  margin-left: 58.33333333%;
}
.col-xs-offset-6 {
  margin-left: 50%;
}
.col-xs-offset-5 {
  margin-left: 41.66666667%;
}
.col-xs-offset-4 {
  margin-left: 33.33333333%;
}
.col-xs-offset-3 {
  margin-left: 25%;
}
.col-xs-offset-2 {
  margin-left: 16.66666667%;
}
.col-xs-offset-1 {
  margin-left: 8.33333333%;
}
.col-xs-offset-0 {
  margin-left: 0%;
}
@media (min-width: 768px) {
  .col-sm-1, .col-sm-2, .col-sm-3, .col-sm-4, .col-sm-5, .col-sm-6, .col-sm-7, .col-sm-8, .col-sm-9, .col-sm-10, .col-sm-11, .col-sm-12 {
    float: left;
  }
  .col-sm-12 {
    width: 100%;
  }
  .col-sm-11 {
    width: 91.66666667%;
  }
  .col-sm-10 {
    width: 83.33333333%;
  }
  .col-sm-9 {
    width: 75%;
  }
  .col-sm-8 {
    width: 66.66666667%;
  }
  .col-sm-7 {
    width: 58.33333333%;
  }
  .col-sm-6 {
    width: 50%;
  }
  .col-sm-5 {
    width: 41.66666667%;
  }
  .col-sm-4 {
    width: 33.33333333%;
  }
  .col-sm-3 {
    width: 25%;
  }
  .col-sm-2 {
    width: 16.66666667%;
  }
  .col-sm-1 {
    width: 8.33333333%;
  }
  .col-sm-pull-12 {
    right: 100%;
  }
  .col-sm-pull-11 {
    right: 91.66666667%;
  }
  .col-sm-pull-10 {
    right: 83.33333333%;
  }
  .col-sm-pull-9 {
    right: 75%;
  }
  .col-sm-pull-8 {
    right: 66.66666667%;
  }
  .col-sm-pull-7 {
    right: 58.33333333%;
  }
  .col-sm-pull-6 {
    right: 50%;
  }
  .col-sm-pull-5 {
    right: 41.66666667%;
  }
  .col-sm-pull-4 {
    right: 33.33333333%;
  }
  .col-sm-pull-3 {
    right: 25%;
  }
  .col-sm-pull-2 {
    right: 16.66666667%;
  }
  .col-sm-pull-1 {
    right: 8.33333333%;
  }
  .col-sm-pull-0 {
    right: auto;
  }
  .col-sm-push-12 {
    left: 100%;
  }
  .col-sm-push-11 {
    left: 91.66666667%;
  }
  .col-sm-push-10 {
    left: 83.33333333%;
  }
  .col-sm-push-9 {
    left: 75%;
  }
  .col-sm-push-8 {
    left: 66.66666667%;
  }
  .col-sm-push-7 {
    left: 58.33333333%;
  }
  .col-sm-push-6 {
    left: 50%;
  }
  .col-sm-push-5 {
    left: 41.66666667%;
  }
  .col-sm-push-4 {
    left: 33.33333333%;
  }
  .col-sm-push-3 {
    left: 25%;
  }
  .col-sm-push-2 {
    left: 16.66666667%;
  }
  .col-sm-push-1 {
    left: 8.33333333%;
  }
  .col-sm-push-0 {
    left: auto;
  }
  .col-sm-offset-12 {
    margin-left: 100%;
  }
  .col-sm-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-sm-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-sm-offset-9 {
    margin-left: 75%;
  }
  .col-sm-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-sm-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-sm-offset-6 {
    margin-left: 50%;
  }
  .col-sm-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-sm-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-sm-offset-3 {
    margin-left: 25%;
  }
  .col-sm-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-sm-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-sm-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 992px) {
  .col-md-1, .col-md-2, .col-md-3, .col-md-4, .col-md-5, .col-md-6, .col-md-7, .col-md-8, .col-md-9, .col-md-10, .col-md-11, .col-md-12 {
    float: left;
  }
  .col-md-12 {
    width: 100%;
  }
  .col-md-11 {
    width: 91.66666667%;
  }
  .col-md-10 {
    width: 83.33333333%;
  }
  .col-md-9 {
    width: 75%;
  }
  .col-md-8 {
    width: 66.66666667%;
  }
  .col-md-7 {
    width: 58.33333333%;
  }
  .col-md-6 {
    width: 50%;
  }
  .col-md-5 {
    width: 41.66666667%;
  }
  .col-md-4 {
    width: 33.33333333%;
  }
  .col-md-3 {
    width: 25%;
  }
  .col-md-2 {
    width: 16.66666667%;
  }
  .col-md-1 {
    width: 8.33333333%;
  }
  .col-md-pull-12 {
    right: 100%;
  }
  .col-md-pull-11 {
    right: 91.66666667%;
  }
  .col-md-pull-10 {
    right: 83.33333333%;
  }
  .col-md-pull-9 {
    right: 75%;
  }
  .col-md-pull-8 {
    right: 66.66666667%;
  }
  .col-md-pull-7 {
    right: 58.33333333%;
  }
  .col-md-pull-6 {
    right: 50%;
  }
  .col-md-pull-5 {
    right: 41.66666667%;
  }
  .col-md-pull-4 {
    right: 33.33333333%;
  }
  .col-md-pull-3 {
    right: 25%;
  }
  .col-md-pull-2 {
    right: 16.66666667%;
  }
  .col-md-pull-1 {
    right: 8.33333333%;
  }
  .col-md-pull-0 {
    right: auto;
  }
  .col-md-push-12 {
    left: 100%;
  }
  .col-md-push-11 {
    left: 91.66666667%;
  }
  .col-md-push-10 {
    left: 83.33333333%;
  }
  .col-md-push-9 {
    left: 75%;
  }
  .col-md-push-8 {
    left: 66.66666667%;
  }
  .col-md-push-7 {
    left: 58.33333333%;
  }
  .col-md-push-6 {
    left: 50%;
  }
  .col-md-push-5 {
    left: 41.66666667%;
  }
  .col-md-push-4 {
    left: 33.33333333%;
  }
  .col-md-push-3 {
    left: 25%;
  }
  .col-md-push-2 {
    left: 16.66666667%;
  }
  .col-md-push-1 {
    left: 8.33333333%;
  }
  .col-md-push-0 {
    left: auto;
  }
  .col-md-offset-12 {
    margin-left: 100%;
  }
  .col-md-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-md-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-md-offset-9 {
    margin-left: 75%;
  }
  .col-md-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-md-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-md-offset-6 {
    margin-left: 50%;
  }
  .col-md-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-md-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-md-offset-3 {
    margin-left: 25%;
  }
  .col-md-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-md-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-md-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 1200px) {
  .col-lg-1, .col-lg-2, .col-lg-3, .col-lg-4, .col-lg-5, .col-lg-6, .col-lg-7, .col-lg-8, .col-lg-9, .col-lg-10, .col-lg-11, .col-lg-12 {
    float: left;
  }
  .col-lg-12 {
    width: 100%;
  }
  .col-lg-11 {
    width: 91.66666667%;
  }
  .col-lg-10 {
    width: 83.33333333%;
  }
  .col-lg-9 {
    width: 75%;
  }
  .col-lg-8 {
    width: 66.66666667%;
  }
  .col-lg-7 {
    width: 58.33333333%;
  }
  .col-lg-6 {
    width: 50%;
  }
  .col-lg-5 {
    width: 41.66666667%;
  }
  .col-lg-4 {
    width: 33.33333333%;
  }
  .col-lg-3 {
    width: 25%;
  }
  .col-lg-2 {
    width: 16.66666667%;
  }
  .col-lg-1 {
    width: 8.33333333%;
  }
  .col-lg-pull-12 {
    right: 100%;
  }
  .col-lg-pull-11 {
    right: 91.66666667%;
  }
  .col-lg-pull-10 {
    right: 83.33333333%;
  }
  .col-lg-pull-9 {
    right: 75%;
  }
  .col-lg-pull-8 {
    right: 66.66666667%;
  }
  .col-lg-pull-7 {
    right: 58.33333333%;
  }
  .col-lg-pull-6 {
    right: 50%;
  }
  .col-lg-pull-5 {
    right: 41.66666667%;
  }
  .col-lg-pull-4 {
    right: 33.33333333%;
  }
  .col-lg-pull-3 {
    right: 25%;
  }
  .col-lg-pull-2 {
    right: 16.66666667%;
  }
  .col-lg-pull-1 {
    right: 8.33333333%;
  }
  .col-lg-pull-0 {
    right: auto;
  }
  .col-lg-push-12 {
    left: 100%;
  }
  .col-lg-push-11 {
    left: 91.66666667%;
  }
  .col-lg-push-10 {
    left: 83.33333333%;
  }
  .col-lg-push-9 {
    left: 75%;
  }
  .col-lg-push-8 {
    left: 66.66666667%;
  }
  .col-lg-push-7 {
    left: 58.33333333%;
  }
  .col-lg-push-6 {
    left: 50%;
  }
  .col-lg-push-5 {
    left: 41.66666667%;
  }
  .col-lg-push-4 {
    left: 33.33333333%;
  }
  .col-lg-push-3 {
    left: 25%;
  }
  .col-lg-push-2 {
    left: 16.66666667%;
  }
  .col-lg-push-1 {
    left: 8.33333333%;
  }
  .col-lg-push-0 {
    left: auto;
  }
  .col-lg-offset-12 {
    margin-left: 100%;
  }
  .col-lg-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-lg-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-lg-offset-9 {
    margin-left: 75%;
  }
  .col-lg-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-lg-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-lg-offset-6 {
    margin-left: 50%;
  }
  .col-lg-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-lg-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-lg-offset-3 {
    margin-left: 25%;
  }
  .col-lg-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-lg-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-lg-offset-0 {
    margin-left: 0%;
  }
}
table {
  background-color: transparent;
}
caption {
  padding-top: 8px;
  padding-bottom: 8px;
  color: #777777;
  text-align: left;
}
th {
  text-align: left;
}
.table {
  width: 100%;
  max-width: 100%;
  margin-bottom: 18px;
}
.table > thead > tr > th,
.table > tbody > tr > th,
.table > tfoot > tr > th,
.table > thead > tr > td,
.table > tbody > tr > td,
.table > tfoot > tr > td {
  padding: 8px;
  line-height: 1.42857143;
  vertical-align: top;
  border-top: 1px solid #ddd;
}
.table > thead > tr > th {
  vertical-align: bottom;
  border-bottom: 2px solid #ddd;
}
.table > caption + thead > tr:first-child > th,
.table > colgroup + thead > tr:first-child > th,
.table > thead:first-child > tr:first-child > th,
.table > caption + thead > tr:first-child > td,
.table > colgroup + thead > tr:first-child > td,
.table > thead:first-child > tr:first-child > td {
  border-top: 0;
}
.table > tbody + tbody {
  border-top: 2px solid #ddd;
}
.table .table {
  background-color: #fff;
}
.table-condensed > thead > tr > th,
.table-condensed > tbody > tr > th,
.table-condensed > tfoot > tr > th,
.table-condensed > thead > tr > td,
.table-condensed > tbody > tr > td,
.table-condensed > tfoot > tr > td {
  padding: 5px;
}
.table-bordered {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > tbody > tr > th,
.table-bordered > tfoot > tr > th,
.table-bordered > thead > tr > td,
.table-bordered > tbody > tr > td,
.table-bordered > tfoot > tr > td {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > thead > tr > td {
  border-bottom-width: 2px;
}
.table-striped > tbody > tr:nth-of-type(odd) {
  background-color: #f9f9f9;
}
.table-hover > tbody > tr:hover {
  background-color: #f5f5f5;
}
table col[class*="col-"] {
  position: static;
  float: none;
  display: table-column;
}
table td[class*="col-"],
table th[class*="col-"] {
  position: static;
  float: none;
  display: table-cell;
}
.table > thead > tr > td.active,
.table > tbody > tr > td.active,
.table > tfoot > tr > td.active,
.table > thead > tr > th.active,
.table > tbody > tr > th.active,
.table > tfoot > tr > th.active,
.table > thead > tr.active > td,
.table > tbody > tr.active > td,
.table > tfoot > tr.active > td,
.table > thead > tr.active > th,
.table > tbody > tr.active > th,
.table > tfoot > tr.active > th {
  background-color: #f5f5f5;
}
.table-hover > tbody > tr > td.active:hover,
.table-hover > tbody > tr > th.active:hover,
.table-hover > tbody > tr.active:hover > td,
.table-hover > tbody > tr:hover > .active,
.table-hover > tbody > tr.active:hover > th {
  background-color: #e8e8e8;
}
.table > thead > tr > td.success,
.table > tbody > tr > td.success,
.table > tfoot > tr > td.success,
.table > thead > tr > th.success,
.table > tbody > tr > th.success,
.table > tfoot > tr > th.success,
.table > thead > tr.success > td,
.table > tbody > tr.success > td,
.table > tfoot > tr.success > td,
.table > thead > tr.success > th,
.table > tbody > tr.success > th,
.table > tfoot > tr.success > th {
  background-color: #dff0d8;
}
.table-hover > tbody > tr > td.success:hover,
.table-hover > tbody > tr > th.success:hover,
.table-hover > tbody > tr.success:hover > td,
.table-hover > tbody > tr:hover > .success,
.table-hover > tbody > tr.success:hover > th {
  background-color: #d0e9c6;
}
.table > thead > tr > td.info,
.table > tbody > tr > td.info,
.table > tfoot > tr > td.info,
.table > thead > tr > th.info,
.table > tbody > tr > th.info,
.table > tfoot > tr > th.info,
.table > thead > tr.info > td,
.table > tbody > tr.info > td,
.table > tfoot > tr.info > td,
.table > thead > tr.info > th,
.table > tbody > tr.info > th,
.table > tfoot > tr.info > th {
  background-color: #d9edf7;
}
.table-hover > tbody > tr > td.info:hover,
.table-hover > tbody > tr > th.info:hover,
.table-hover > tbody > tr.info:hover > td,
.table-hover > tbody > tr:hover > .info,
.table-hover > tbody > tr.info:hover > th {
  background-color: #c4e3f3;
}
.table > thead > tr > td.warning,
.table > tbody > tr > td.warning,
.table > tfoot > tr > td.warning,
.table > thead > tr > th.warning,
.table > tbody > tr > th.warning,
.table > tfoot > tr > th.warning,
.table > thead > tr.warning > td,
.table > tbody > tr.warning > td,
.table > tfoot > tr.warning > td,
.table > thead > tr.warning > th,
.table > tbody > tr.warning > th,
.table > tfoot > tr.warning > th {
  background-color: #fcf8e3;
}
.table-hover > tbody > tr > td.warning:hover,
.table-hover > tbody > tr > th.warning:hover,
.table-hover > tbody > tr.warning:hover > td,
.table-hover > tbody > tr:hover > .warning,
.table-hover > tbody > tr.warning:hover > th {
  background-color: #faf2cc;
}
.table > thead > tr > td.danger,
.table > tbody > tr > td.danger,
.table > tfoot > tr > td.danger,
.table > thead > tr > th.danger,
.table > tbody > tr > th.danger,
.table > tfoot > tr > th.danger,
.table > thead > tr.danger > td,
.table > tbody > tr.danger > td,
.table > tfoot > tr.danger > td,
.table > thead > tr.danger > th,
.table > tbody > tr.danger > th,
.table > tfoot > tr.danger > th {
  background-color: #f2dede;
}
.table-hover > tbody > tr > td.danger:hover,
.table-hover > tbody > tr > th.danger:hover,
.table-hover > tbody > tr.danger:hover > td,
.table-hover > tbody > tr:hover > .danger,
.table-hover > tbody > tr.danger:hover > th {
  background-color: #ebcccc;
}
.table-responsive {
  overflow-x: auto;
  min-height: 0.01%;
}
@media screen and (max-width: 767px) {
  .table-responsive {
    width: 100%;
    margin-bottom: 13.5px;
    overflow-y: hidden;
    -ms-overflow-style: -ms-autohiding-scrollbar;
    border: 1px solid #ddd;
  }
  .table-responsive > .table {
    margin-bottom: 0;
  }
  .table-responsive > .table > thead > tr > th,
  .table-responsive > .table > tbody > tr > th,
  .table-responsive > .table > tfoot > tr > th,
  .table-responsive > .table > thead > tr > td,
  .table-responsive > .table > tbody > tr > td,
  .table-responsive > .table > tfoot > tr > td {
    white-space: nowrap;
  }
  .table-responsive > .table-bordered {
    border: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:first-child,
  .table-responsive > .table-bordered > tbody > tr > th:first-child,
  .table-responsive > .table-bordered > tfoot > tr > th:first-child,
  .table-responsive > .table-bordered > thead > tr > td:first-child,
  .table-responsive > .table-bordered > tbody > tr > td:first-child,
  .table-responsive > .table-bordered > tfoot > tr > td:first-child {
    border-left: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:last-child,
  .table-responsive > .table-bordered > tbody > tr > th:last-child,
  .table-responsive > .table-bordered > tfoot > tr > th:last-child,
  .table-responsive > .table-bordered > thead > tr > td:last-child,
  .table-responsive > .table-bordered > tbody > tr > td:last-child,
  .table-responsive > .table-bordered > tfoot > tr > td:last-child {
    border-right: 0;
  }
  .table-responsive > .table-bordered > tbody > tr:last-child > th,
  .table-responsive > .table-bordered > tfoot > tr:last-child > th,
  .table-responsive > .table-bordered > tbody > tr:last-child > td,
  .table-responsive > .table-bordered > tfoot > tr:last-child > td {
    border-bottom: 0;
  }
}
fieldset {
  padding: 0;
  margin: 0;
  border: 0;
  min-width: 0;
}
legend {
  display: block;
  width: 100%;
  padding: 0;
  margin-bottom: 18px;
  font-size: 19.5px;
  line-height: inherit;
  color: #333333;
  border: 0;
  border-bottom: 1px solid #e5e5e5;
}
label {
  display: inline-block;
  max-width: 100%;
  margin-bottom: 5px;
  font-weight: bold;
}
input[type="search"] {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
input[type="radio"],
input[type="checkbox"] {
  margin: 4px 0 0;
  margin-top: 1px \9;
  line-height: normal;
}
input[type="file"] {
  display: block;
}
input[type="range"] {
  display: block;
  width: 100%;
}
select[multiple],
select[size] {
  height: auto;
}
input[type="file"]:focus,
input[type="radio"]:focus,
input[type="checkbox"]:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
output {
  display: block;
  padding-top: 7px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
}
.form-control {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
}
.form-control:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.form-control::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.form-control:-ms-input-placeholder {
  color: #999;
}
.form-control::-webkit-input-placeholder {
  color: #999;
}
.form-control::-ms-expand {
  border: 0;
  background-color: transparent;
}
.form-control[disabled],
.form-control[readonly],
fieldset[disabled] .form-control {
  background-color: #eeeeee;
  opacity: 1;
}
.form-control[disabled],
fieldset[disabled] .form-control {
  cursor: not-allowed;
}
textarea.form-control {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: none;
}
@media screen and (-webkit-min-device-pixel-ratio: 0) {
  input[type="date"].form-control,
  input[type="time"].form-control,
  input[type="datetime-local"].form-control,
  input[type="month"].form-control {
    line-height: 32px;
  }
  input[type="date"].input-sm,
  input[type="time"].input-sm,
  input[type="datetime-local"].input-sm,
  input[type="month"].input-sm,
  .input-group-sm input[type="date"],
  .input-group-sm input[type="time"],
  .input-group-sm input[type="datetime-local"],
  .input-group-sm input[type="month"] {
    line-height: 30px;
  }
  input[type="date"].input-lg,
  input[type="time"].input-lg,
  input[type="datetime-local"].input-lg,
  input[type="month"].input-lg,
  .input-group-lg input[type="date"],
  .input-group-lg input[type="time"],
  .input-group-lg input[type="datetime-local"],
  .input-group-lg input[type="month"] {
    line-height: 45px;
  }
}
.form-group {
  margin-bottom: 15px;
}
.radio,
.checkbox {
  position: relative;
  display: block;
  margin-top: 10px;
  margin-bottom: 10px;
}
.radio label,
.checkbox label {
  min-height: 18px;
  padding-left: 20px;
  margin-bottom: 0;
  font-weight: normal;
  cursor: pointer;
}
.radio input[type="radio"],
.radio-inline input[type="radio"],
.checkbox input[type="checkbox"],
.checkbox-inline input[type="checkbox"] {
  position: absolute;
  margin-left: -20px;
  margin-top: 4px \9;
}
.radio + .radio,
.checkbox + .checkbox {
  margin-top: -5px;
}
.radio-inline,
.checkbox-inline {
  position: relative;
  display: inline-block;
  padding-left: 20px;
  margin-bottom: 0;
  vertical-align: middle;
  font-weight: normal;
  cursor: pointer;
}
.radio-inline + .radio-inline,
.checkbox-inline + .checkbox-inline {
  margin-top: 0;
  margin-left: 10px;
}
input[type="radio"][disabled],
input[type="checkbox"][disabled],
input[type="radio"].disabled,
input[type="checkbox"].disabled,
fieldset[disabled] input[type="radio"],
fieldset[disabled] input[type="checkbox"] {
  cursor: not-allowed;
}
.radio-inline.disabled,
.checkbox-inline.disabled,
fieldset[disabled] .radio-inline,
fieldset[disabled] .checkbox-inline {
  cursor: not-allowed;
}
.radio.disabled label,
.checkbox.disabled label,
fieldset[disabled] .radio label,
fieldset[disabled] .checkbox label {
  cursor: not-allowed;
}
.form-control-static {
  padding-top: 7px;
  padding-bottom: 7px;
  margin-bottom: 0;
  min-height: 31px;
}
.form-control-static.input-lg,
.form-control-static.input-sm {
  padding-left: 0;
  padding-right: 0;
}
.input-sm {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-sm {
  height: 30px;
  line-height: 30px;
}
textarea.input-sm,
select[multiple].input-sm {
  height: auto;
}
.form-group-sm .form-control {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.form-group-sm select.form-control {
  height: 30px;
  line-height: 30px;
}
.form-group-sm textarea.form-control,
.form-group-sm select[multiple].form-control {
  height: auto;
}
.form-group-sm .form-control-static {
  height: 30px;
  min-height: 30px;
  padding: 6px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.input-lg {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-lg {
  height: 45px;
  line-height: 45px;
}
textarea.input-lg,
select[multiple].input-lg {
  height: auto;
}
.form-group-lg .form-control {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.form-group-lg select.form-control {
  height: 45px;
  line-height: 45px;
}
.form-group-lg textarea.form-control,
.form-group-lg select[multiple].form-control {
  height: auto;
}
.form-group-lg .form-control-static {
  height: 45px;
  min-height: 35px;
  padding: 11px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.has-feedback {
  position: relative;
}
.has-feedback .form-control {
  padding-right: 40px;
}
.form-control-feedback {
  position: absolute;
  top: 0;
  right: 0;
  z-index: 2;
  display: block;
  width: 32px;
  height: 32px;
  line-height: 32px;
  text-align: center;
  pointer-events: none;
}
.input-lg + .form-control-feedback,
.input-group-lg + .form-control-feedback,
.form-group-lg .form-control + .form-control-feedback {
  width: 45px;
  height: 45px;
  line-height: 45px;
}
.input-sm + .form-control-feedback,
.input-group-sm + .form-control-feedback,
.form-group-sm .form-control + .form-control-feedback {
  width: 30px;
  height: 30px;
  line-height: 30px;
}
.has-success .help-block,
.has-success .control-label,
.has-success .radio,
.has-success .checkbox,
.has-success .radio-inline,
.has-success .checkbox-inline,
.has-success.radio label,
.has-success.checkbox label,
.has-success.radio-inline label,
.has-success.checkbox-inline label {
  color: #3c763d;
}
.has-success .form-control {
  border-color: #3c763d;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-success .form-control:focus {
  border-color: #2b542c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
}
.has-success .input-group-addon {
  color: #3c763d;
  border-color: #3c763d;
  background-color: #dff0d8;
}
.has-success .form-control-feedback {
  color: #3c763d;
}
.has-warning .help-block,
.has-warning .control-label,
.has-warning .radio,
.has-warning .checkbox,
.has-warning .radio-inline,
.has-warning .checkbox-inline,
.has-warning.radio label,
.has-warning.checkbox label,
.has-warning.radio-inline label,
.has-warning.checkbox-inline label {
  color: #8a6d3b;
}
.has-warning .form-control {
  border-color: #8a6d3b;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-warning .form-control:focus {
  border-color: #66512c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
}
.has-warning .input-group-addon {
  color: #8a6d3b;
  border-color: #8a6d3b;
  background-color: #fcf8e3;
}
.has-warning .form-control-feedback {
  color: #8a6d3b;
}
.has-error .help-block,
.has-error .control-label,
.has-error .radio,
.has-error .checkbox,
.has-error .radio-inline,
.has-error .checkbox-inline,
.has-error.radio label,
.has-error.checkbox label,
.has-error.radio-inline label,
.has-error.checkbox-inline label {
  color: #a94442;
}
.has-error .form-control {
  border-color: #a94442;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-error .form-control:focus {
  border-color: #843534;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
}
.has-error .input-group-addon {
  color: #a94442;
  border-color: #a94442;
  background-color: #f2dede;
}
.has-error .form-control-feedback {
  color: #a94442;
}
.has-feedback label ~ .form-control-feedback {
  top: 23px;
}
.has-feedback label.sr-only ~ .form-control-feedback {
  top: 0;
}
.help-block {
  display: block;
  margin-top: 5px;
  margin-bottom: 10px;
  color: #404040;
}
@media (min-width: 768px) {
  .form-inline .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .form-inline .form-control-static {
    display: inline-block;
  }
  .form-inline .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .form-inline .input-group .input-group-addon,
  .form-inline .input-group .input-group-btn,
  .form-inline .input-group .form-control {
    width: auto;
  }
  .form-inline .input-group > .form-control {
    width: 100%;
  }
  .form-inline .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio,
  .form-inline .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio label,
  .form-inline .checkbox label {
    padding-left: 0;
  }
  .form-inline .radio input[type="radio"],
  .form-inline .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .form-inline .has-feedback .form-control-feedback {
    top: 0;
  }
}
.form-horizontal .radio,
.form-horizontal .checkbox,
.form-horizontal .radio-inline,
.form-horizontal .checkbox-inline {
  margin-top: 0;
  margin-bottom: 0;
  padding-top: 7px;
}
.form-horizontal .radio,
.form-horizontal .checkbox {
  min-height: 25px;
}
.form-horizontal .form-group {
  margin-left: 0px;
  margin-right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .control-label {
    text-align: right;
    margin-bottom: 0;
    padding-top: 7px;
  }
}
.form-horizontal .has-feedback .form-control-feedback {
  right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .form-group-lg .control-label {
    padding-top: 11px;
    font-size: 17px;
  }
}
@media (min-width: 768px) {
  .form-horizontal .form-group-sm .control-label {
    padding-top: 6px;
    font-size: 12px;
  }
}
.btn {
  display: inline-block;
  margin-bottom: 0;
  font-weight: normal;
  text-align: center;
  vertical-align: middle;
  touch-action: manipulation;
  cursor: pointer;
  background-image: none;
  border: 1px solid transparent;
  white-space: nowrap;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  border-radius: 2px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
.btn:focus,
.btn:active:focus,
.btn.active:focus,
.btn.focus,
.btn:active.focus,
.btn.active.focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
.btn:hover,
.btn:focus,
.btn.focus {
  color: #333;
  text-decoration: none;
}
.btn:active,
.btn.active {
  outline: 0;
  background-image: none;
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn.disabled,
.btn[disabled],
fieldset[disabled] .btn {
  cursor: not-allowed;
  opacity: 0.65;
  filter: alpha(opacity=65);
  -webkit-box-shadow: none;
  box-shadow: none;
}
a.btn.disabled,
fieldset[disabled] a.btn {
  pointer-events: none;
}
.btn-default {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.btn-default:focus,
.btn-default.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.btn-default:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active:hover,
.btn-default.active:hover,
.open > .dropdown-toggle.btn-default:hover,
.btn-default:active:focus,
.btn-default.active:focus,
.open > .dropdown-toggle.btn-default:focus,
.btn-default:active.focus,
.btn-default.active.focus,
.open > .dropdown-toggle.btn-default.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  background-image: none;
}
.btn-default.disabled:hover,
.btn-default[disabled]:hover,
fieldset[disabled] .btn-default:hover,
.btn-default.disabled:focus,
.btn-default[disabled]:focus,
fieldset[disabled] .btn-default:focus,
.btn-default.disabled.focus,
.btn-default[disabled].focus,
fieldset[disabled] .btn-default.focus {
  background-color: #fff;
  border-color: #ccc;
}
.btn-default .badge {
  color: #fff;
  background-color: #333;
}
.btn-primary {
  color: #fff;
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary:focus,
.btn-primary.focus {
  color: #fff;
  background-color: #286090;
  border-color: #122b40;
}
.btn-primary:hover {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active:hover,
.btn-primary.active:hover,
.open > .dropdown-toggle.btn-primary:hover,
.btn-primary:active:focus,
.btn-primary.active:focus,
.open > .dropdown-toggle.btn-primary:focus,
.btn-primary:active.focus,
.btn-primary.active.focus,
.open > .dropdown-toggle.btn-primary.focus {
  color: #fff;
  background-color: #204d74;
  border-color: #122b40;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  background-image: none;
}
.btn-primary.disabled:hover,
.btn-primary[disabled]:hover,
fieldset[disabled] .btn-primary:hover,
.btn-primary.disabled:focus,
.btn-primary[disabled]:focus,
fieldset[disabled] .btn-primary:focus,
.btn-primary.disabled.focus,
.btn-primary[disabled].focus,
fieldset[disabled] .btn-primary.focus {
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary .badge {
  color: #337ab7;
  background-color: #fff;
}
.btn-success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success:focus,
.btn-success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.btn-success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active:hover,
.btn-success.active:hover,
.open > .dropdown-toggle.btn-success:hover,
.btn-success:active:focus,
.btn-success.active:focus,
.open > .dropdown-toggle.btn-success:focus,
.btn-success:active.focus,
.btn-success.active.focus,
.open > .dropdown-toggle.btn-success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  background-image: none;
}
.btn-success.disabled:hover,
.btn-success[disabled]:hover,
fieldset[disabled] .btn-success:hover,
.btn-success.disabled:focus,
.btn-success[disabled]:focus,
fieldset[disabled] .btn-success:focus,
.btn-success.disabled.focus,
.btn-success[disabled].focus,
fieldset[disabled] .btn-success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.btn-info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info:focus,
.btn-info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.btn-info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active:hover,
.btn-info.active:hover,
.open > .dropdown-toggle.btn-info:hover,
.btn-info:active:focus,
.btn-info.active:focus,
.open > .dropdown-toggle.btn-info:focus,
.btn-info:active.focus,
.btn-info.active.focus,
.open > .dropdown-toggle.btn-info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  background-image: none;
}
.btn-info.disabled:hover,
.btn-info[disabled]:hover,
fieldset[disabled] .btn-info:hover,
.btn-info.disabled:focus,
.btn-info[disabled]:focus,
fieldset[disabled] .btn-info:focus,
.btn-info.disabled.focus,
.btn-info[disabled].focus,
fieldset[disabled] .btn-info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.btn-warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning:focus,
.btn-warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.btn-warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active:hover,
.btn-warning.active:hover,
.open > .dropdown-toggle.btn-warning:hover,
.btn-warning:active:focus,
.btn-warning.active:focus,
.open > .dropdown-toggle.btn-warning:focus,
.btn-warning:active.focus,
.btn-warning.active.focus,
.open > .dropdown-toggle.btn-warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  background-image: none;
}
.btn-warning.disabled:hover,
.btn-warning[disabled]:hover,
fieldset[disabled] .btn-warning:hover,
.btn-warning.disabled:focus,
.btn-warning[disabled]:focus,
fieldset[disabled] .btn-warning:focus,
.btn-warning.disabled.focus,
.btn-warning[disabled].focus,
fieldset[disabled] .btn-warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.btn-danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger:focus,
.btn-danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.btn-danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active:hover,
.btn-danger.active:hover,
.open > .dropdown-toggle.btn-danger:hover,
.btn-danger:active:focus,
.btn-danger.active:focus,
.open > .dropdown-toggle.btn-danger:focus,
.btn-danger:active.focus,
.btn-danger.active.focus,
.open > .dropdown-toggle.btn-danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  background-image: none;
}
.btn-danger.disabled:hover,
.btn-danger[disabled]:hover,
fieldset[disabled] .btn-danger:hover,
.btn-danger.disabled:focus,
.btn-danger[disabled]:focus,
fieldset[disabled] .btn-danger:focus,
.btn-danger.disabled.focus,
.btn-danger[disabled].focus,
fieldset[disabled] .btn-danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger .badge {
  color: #d9534f;
  background-color: #fff;
}
.btn-link {
  color: #337ab7;
  font-weight: normal;
  border-radius: 0;
}
.btn-link,
.btn-link:active,
.btn-link.active,
.btn-link[disabled],
fieldset[disabled] .btn-link {
  background-color: transparent;
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn-link,
.btn-link:hover,
.btn-link:focus,
.btn-link:active {
  border-color: transparent;
}
.btn-link:hover,
.btn-link:focus {
  color: #23527c;
  text-decoration: underline;
  background-color: transparent;
}
.btn-link[disabled]:hover,
fieldset[disabled] .btn-link:hover,
.btn-link[disabled]:focus,
fieldset[disabled] .btn-link:focus {
  color: #777777;
  text-decoration: none;
}
.btn-lg,
.btn-group-lg > .btn {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.btn-sm,
.btn-group-sm > .btn {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-xs,
.btn-group-xs > .btn {
  padding: 1px 5px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-block {
  display: block;
  width: 100%;
}
.btn-block + .btn-block {
  margin-top: 5px;
}
input[type="submit"].btn-block,
input[type="reset"].btn-block,
input[type="button"].btn-block {
  width: 100%;
}
.fade {
  opacity: 0;
  -webkit-transition: opacity 0.15s linear;
  -o-transition: opacity 0.15s linear;
  transition: opacity 0.15s linear;
}
.fade.in {
  opacity: 1;
}
.collapse {
  display: none;
}
.collapse.in {
  display: block;
}
tr.collapse.in {
  display: table-row;
}
tbody.collapse.in {
  display: table-row-group;
}
.collapsing {
  position: relative;
  height: 0;
  overflow: hidden;
  -webkit-transition-property: height, visibility;
  transition-property: height, visibility;
  -webkit-transition-duration: 0.35s;
  transition-duration: 0.35s;
  -webkit-transition-timing-function: ease;
  transition-timing-function: ease;
}
.caret {
  display: inline-block;
  width: 0;
  height: 0;
  margin-left: 2px;
  vertical-align: middle;
  border-top: 4px dashed;
  border-top: 4px solid \9;
  border-right: 4px solid transparent;
  border-left: 4px solid transparent;
}
.dropup,
.dropdown {
  position: relative;
}
.dropdown-toggle:focus {
  outline: 0;
}
.dropdown-menu {
  position: absolute;
  top: 100%;
  left: 0;
  z-index: 1000;
  display: none;
  float: left;
  min-width: 160px;
  padding: 5px 0;
  margin: 2px 0 0;
  list-style: none;
  font-size: 13px;
  text-align: left;
  background-color: #fff;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.15);
  border-radius: 2px;
  -webkit-box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  background-clip: padding-box;
}
.dropdown-menu.pull-right {
  right: 0;
  left: auto;
}
.dropdown-menu .divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.dropdown-menu > li > a {
  display: block;
  padding: 3px 20px;
  clear: both;
  font-weight: normal;
  line-height: 1.42857143;
  color: #333333;
  white-space: nowrap;
}
.dropdown-menu > li > a:hover,
.dropdown-menu > li > a:focus {
  text-decoration: none;
  color: #262626;
  background-color: #f5f5f5;
}
.dropdown-menu > .active > a,
.dropdown-menu > .active > a:hover,
.dropdown-menu > .active > a:focus {
  color: #fff;
  text-decoration: none;
  outline: 0;
  background-color: #337ab7;
}
.dropdown-menu > .disabled > a,
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  color: #777777;
}
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  text-decoration: none;
  background-color: transparent;
  background-image: none;
  filter: progid:DXImageTransform.Microsoft.gradient(enabled = false);
  cursor: not-allowed;
}
.open > .dropdown-menu {
  display: block;
}
.open > a {
  outline: 0;
}
.dropdown-menu-right {
  left: auto;
  right: 0;
}
.dropdown-menu-left {
  left: 0;
  right: auto;
}
.dropdown-header {
  display: block;
  padding: 3px 20px;
  font-size: 12px;
  line-height: 1.42857143;
  color: #777777;
  white-space: nowrap;
}
.dropdown-backdrop {
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
  top: 0;
  z-index: 990;
}
.pull-right > .dropdown-menu {
  right: 0;
  left: auto;
}
.dropup .caret,
.navbar-fixed-bottom .dropdown .caret {
  border-top: 0;
  border-bottom: 4px dashed;
  border-bottom: 4px solid \9;
  content: "";
}
.dropup .dropdown-menu,
.navbar-fixed-bottom .dropdown .dropdown-menu {
  top: auto;
  bottom: 100%;
  margin-bottom: 2px;
}
@media (min-width: 541px) {
  .navbar-right .dropdown-menu {
    left: auto;
    right: 0;
  }
  .navbar-right .dropdown-menu-left {
    left: 0;
    right: auto;
  }
}
.btn-group,
.btn-group-vertical {
  position: relative;
  display: inline-block;
  vertical-align: middle;
}
.btn-group > .btn,
.btn-group-vertical > .btn {
  position: relative;
  float: left;
}
.btn-group > .btn:hover,
.btn-group-vertical > .btn:hover,
.btn-group > .btn:focus,
.btn-group-vertical > .btn:focus,
.btn-group > .btn:active,
.btn-group-vertical > .btn:active,
.btn-group > .btn.active,
.btn-group-vertical > .btn.active {
  z-index: 2;
}
.btn-group .btn + .btn,
.btn-group .btn + .btn-group,
.btn-group .btn-group + .btn,
.btn-group .btn-group + .btn-group {
  margin-left: -1px;
}
.btn-toolbar {
  margin-left: -5px;
}
.btn-toolbar .btn,
.btn-toolbar .btn-group,
.btn-toolbar .input-group {
  float: left;
}
.btn-toolbar > .btn,
.btn-toolbar > .btn-group,
.btn-toolbar > .input-group {
  margin-left: 5px;
}
.btn-group > .btn:not(:first-child):not(:last-child):not(.dropdown-toggle) {
  border-radius: 0;
}
.btn-group > .btn:first-child {
  margin-left: 0;
}
.btn-group > .btn:first-child:not(:last-child):not(.dropdown-toggle) {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn:last-child:not(:first-child),
.btn-group > .dropdown-toggle:not(:first-child) {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group > .btn-group {
  float: left;
}
.btn-group > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group .dropdown-toggle:active,
.btn-group.open .dropdown-toggle {
  outline: 0;
}
.btn-group > .btn + .dropdown-toggle {
  padding-left: 8px;
  padding-right: 8px;
}
.btn-group > .btn-lg + .dropdown-toggle {
  padding-left: 12px;
  padding-right: 12px;
}
.btn-group.open .dropdown-toggle {
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn-group.open .dropdown-toggle.btn-link {
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn .caret {
  margin-left: 0;
}
.btn-lg .caret {
  border-width: 5px 5px 0;
  border-bottom-width: 0;
}
.dropup .btn-lg .caret {
  border-width: 0 5px 5px;
}
.btn-group-vertical > .btn,
.btn-group-vertical > .btn-group,
.btn-group-vertical > .btn-group > .btn {
  display: block;
  float: none;
  width: 100%;
  max-width: 100%;
}
.btn-group-vertical > .btn-group > .btn {
  float: none;
}
.btn-group-vertical > .btn + .btn,
.btn-group-vertical > .btn + .btn-group,
.btn-group-vertical > .btn-group + .btn,
.btn-group-vertical > .btn-group + .btn-group {
  margin-top: -1px;
  margin-left: 0;
}
.btn-group-vertical > .btn:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.btn-group-vertical > .btn:first-child:not(:last-child) {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn:last-child:not(:first-child) {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
.btn-group-vertical > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.btn-group-justified {
  display: table;
  width: 100%;
  table-layout: fixed;
  border-collapse: separate;
}
.btn-group-justified > .btn,
.btn-group-justified > .btn-group {
  float: none;
  display: table-cell;
  width: 1%;
}
.btn-group-justified > .btn-group .btn {
  width: 100%;
}
.btn-group-justified > .btn-group .dropdown-menu {
  left: auto;
}
[data-toggle="buttons"] > .btn input[type="radio"],
[data-toggle="buttons"] > .btn-group > .btn input[type="radio"],
[data-toggle="buttons"] > .btn input[type="checkbox"],
[data-toggle="buttons"] > .btn-group > .btn input[type="checkbox"] {
  position: absolute;
  clip: rect(0, 0, 0, 0);
  pointer-events: none;
}
.input-group {
  position: relative;
  display: table;
  border-collapse: separate;
}
.input-group[class*="col-"] {
  float: none;
  padding-left: 0;
  padding-right: 0;
}
.input-group .form-control {
  position: relative;
  z-index: 2;
  float: left;
  width: 100%;
  margin-bottom: 0;
}
.input-group .form-control:focus {
  z-index: 3;
}
.input-group-lg > .form-control,
.input-group-lg > .input-group-addon,
.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-group-lg > .form-control,
select.input-group-lg > .input-group-addon,
select.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  line-height: 45px;
}
textarea.input-group-lg > .form-control,
textarea.input-group-lg > .input-group-addon,
textarea.input-group-lg > .input-group-btn > .btn,
select[multiple].input-group-lg > .form-control,
select[multiple].input-group-lg > .input-group-addon,
select[multiple].input-group-lg > .input-group-btn > .btn {
  height: auto;
}
.input-group-sm > .form-control,
.input-group-sm > .input-group-addon,
.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-group-sm > .form-control,
select.input-group-sm > .input-group-addon,
select.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  line-height: 30px;
}
textarea.input-group-sm > .form-control,
textarea.input-group-sm > .input-group-addon,
textarea.input-group-sm > .input-group-btn > .btn,
select[multiple].input-group-sm > .form-control,
select[multiple].input-group-sm > .input-group-addon,
select[multiple].input-group-sm > .input-group-btn > .btn {
  height: auto;
}
.input-group-addon,
.input-group-btn,
.input-group .form-control {
  display: table-cell;
}
.input-group-addon:not(:first-child):not(:last-child),
.input-group-btn:not(:first-child):not(:last-child),
.input-group .form-control:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.input-group-addon,
.input-group-btn {
  width: 1%;
  white-space: nowrap;
  vertical-align: middle;
}
.input-group-addon {
  padding: 6px 12px;
  font-size: 13px;
  font-weight: normal;
  line-height: 1;
  color: #555555;
  text-align: center;
  background-color: #eeeeee;
  border: 1px solid #ccc;
  border-radius: 2px;
}
.input-group-addon.input-sm {
  padding: 5px 10px;
  font-size: 12px;
  border-radius: 1px;
}
.input-group-addon.input-lg {
  padding: 10px 16px;
  font-size: 17px;
  border-radius: 3px;
}
.input-group-addon input[type="radio"],
.input-group-addon input[type="checkbox"] {
  margin-top: 0;
}
.input-group .form-control:first-child,
.input-group-addon:first-child,
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group > .btn,
.input-group-btn:first-child > .dropdown-toggle,
.input-group-btn:last-child > .btn:not(:last-child):not(.dropdown-toggle),
.input-group-btn:last-child > .btn-group:not(:last-child) > .btn {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.input-group-addon:first-child {
  border-right: 0;
}
.input-group .form-control:last-child,
.input-group-addon:last-child,
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group > .btn,
.input-group-btn:last-child > .dropdown-toggle,
.input-group-btn:first-child > .btn:not(:first-child),
.input-group-btn:first-child > .btn-group:not(:first-child) > .btn {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.input-group-addon:last-child {
  border-left: 0;
}
.input-group-btn {
  position: relative;
  font-size: 0;
  white-space: nowrap;
}
.input-group-btn > .btn {
  position: relative;
}
.input-group-btn > .btn + .btn {
  margin-left: -1px;
}
.input-group-btn > .btn:hover,
.input-group-btn > .btn:focus,
.input-group-btn > .btn:active {
  z-index: 2;
}
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group {
  margin-right: -1px;
}
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group {
  z-index: 2;
  margin-left: -1px;
}
.nav {
  margin-bottom: 0;
  padding-left: 0;
  list-style: none;
}
.nav > li {
  position: relative;
  display: block;
}
.nav > li > a {
  position: relative;
  display: block;
  padding: 10px 15px;
}
.nav > li > a:hover,
.nav > li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.nav > li.disabled > a {
  color: #777777;
}
.nav > li.disabled > a:hover,
.nav > li.disabled > a:focus {
  color: #777777;
  text-decoration: none;
  background-color: transparent;
  cursor: not-allowed;
}
.nav .open > a,
.nav .open > a:hover,
.nav .open > a:focus {
  background-color: #eeeeee;
  border-color: #337ab7;
}
.nav .nav-divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.nav > li > a > img {
  max-width: none;
}
.nav-tabs {
  border-bottom: 1px solid #ddd;
}
.nav-tabs > li {
  float: left;
  margin-bottom: -1px;
}
.nav-tabs > li > a {
  margin-right: 2px;
  line-height: 1.42857143;
  border: 1px solid transparent;
  border-radius: 2px 2px 0 0;
}
.nav-tabs > li > a:hover {
  border-color: #eeeeee #eeeeee #ddd;
}
.nav-tabs > li.active > a,
.nav-tabs > li.active > a:hover,
.nav-tabs > li.active > a:focus {
  color: #555555;
  background-color: #fff;
  border: 1px solid #ddd;
  border-bottom-color: transparent;
  cursor: default;
}
.nav-tabs.nav-justified {
  width: 100%;
  border-bottom: 0;
}
.nav-tabs.nav-justified > li {
  float: none;
}
.nav-tabs.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-tabs.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-tabs.nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs.nav-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs.nav-justified > .active > a,
.nav-tabs.nav-justified > .active > a:hover,
.nav-tabs.nav-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs.nav-justified > .active > a,
  .nav-tabs.nav-justified > .active > a:hover,
  .nav-tabs.nav-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.nav-pills > li {
  float: left;
}
.nav-pills > li > a {
  border-radius: 2px;
}
.nav-pills > li + li {
  margin-left: 2px;
}
.nav-pills > li.active > a,
.nav-pills > li.active > a:hover,
.nav-pills > li.active > a:focus {
  color: #fff;
  background-color: #337ab7;
}
.nav-stacked > li {
  float: none;
}
.nav-stacked > li + li {
  margin-top: 2px;
  margin-left: 0;
}
.nav-justified {
  width: 100%;
}
.nav-justified > li {
  float: none;
}
.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs-justified {
  border-bottom: 0;
}
.nav-tabs-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs-justified > .active > a,
.nav-tabs-justified > .active > a:hover,
.nav-tabs-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs-justified > .active > a,
  .nav-tabs-justified > .active > a:hover,
  .nav-tabs-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.tab-content > .tab-pane {
  display: none;
}
.tab-content > .active {
  display: block;
}
.nav-tabs .dropdown-menu {
  margin-top: -1px;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar {
  position: relative;
  min-height: 30px;
  margin-bottom: 18px;
  border: 1px solid transparent;
}
@media (min-width: 541px) {
  .navbar {
    border-radius: 2px;
  }
}
@media (min-width: 541px) {
  .navbar-header {
    float: left;
  }
}
.navbar-collapse {
  overflow-x: visible;
  padding-right: 0px;
  padding-left: 0px;
  border-top: 1px solid transparent;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1);
  -webkit-overflow-scrolling: touch;
}
.navbar-collapse.in {
  overflow-y: auto;
}
@media (min-width: 541px) {
  .navbar-collapse {
    width: auto;
    border-top: 0;
    box-shadow: none;
  }
  .navbar-collapse.collapse {
    display: block !important;
    height: auto !important;
    padding-bottom: 0;
    overflow: visible !important;
  }
  .navbar-collapse.in {
    overflow-y: visible;
  }
  .navbar-fixed-top .navbar-collapse,
  .navbar-static-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    padding-left: 0;
    padding-right: 0;
  }
}
.navbar-fixed-top .navbar-collapse,
.navbar-fixed-bottom .navbar-collapse {
  max-height: 340px;
}
@media (max-device-width: 540px) and (orientation: landscape) {
  .navbar-fixed-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    max-height: 200px;
  }
}
.container > .navbar-header,
.container-fluid > .navbar-header,
.container > .navbar-collapse,
.container-fluid > .navbar-collapse {
  margin-right: 0px;
  margin-left: 0px;
}
@media (min-width: 541px) {
  .container > .navbar-header,
  .container-fluid > .navbar-header,
  .container > .navbar-collapse,
  .container-fluid > .navbar-collapse {
    margin-right: 0;
    margin-left: 0;
  }
}
.navbar-static-top {
  z-index: 1000;
  border-width: 0 0 1px;
}
@media (min-width: 541px) {
  .navbar-static-top {
    border-radius: 0;
  }
}
.navbar-fixed-top,
.navbar-fixed-bottom {
  position: fixed;
  right: 0;
  left: 0;
  z-index: 1030;
}
@media (min-width: 541px) {
  .navbar-fixed-top,
  .navbar-fixed-bottom {
    border-radius: 0;
  }
}
.navbar-fixed-top {
  top: 0;
  border-width: 0 0 1px;
}
.navbar-fixed-bottom {
  bottom: 0;
  margin-bottom: 0;
  border-width: 1px 0 0;
}
.navbar-brand {
  float: left;
  padding: 6px 0px;
  font-size: 17px;
  line-height: 18px;
  height: 30px;
}
.navbar-brand:hover,
.navbar-brand:focus {
  text-decoration: none;
}
.navbar-brand > img {
  display: block;
}
@media (min-width: 541px) {
  .navbar > .container .navbar-brand,
  .navbar > .container-fluid .navbar-brand {
    margin-left: 0px;
  }
}
.navbar-toggle {
  position: relative;
  float: right;
  margin-right: 0px;
  padding: 9px 10px;
  margin-top: -2px;
  margin-bottom: -2px;
  background-color: transparent;
  background-image: none;
  border: 1px solid transparent;
  border-radius: 2px;
}
.navbar-toggle:focus {
  outline: 0;
}
.navbar-toggle .icon-bar {
  display: block;
  width: 22px;
  height: 2px;
  border-radius: 1px;
}
.navbar-toggle .icon-bar + .icon-bar {
  margin-top: 4px;
}
@media (min-width: 541px) {
  .navbar-toggle {
    display: none;
  }
}
.navbar-nav {
  margin: 3px 0px;
}
.navbar-nav > li > a {
  padding-top: 10px;
  padding-bottom: 10px;
  line-height: 18px;
}
@media (max-width: 540px) {
  .navbar-nav .open .dropdown-menu {
    position: static;
    float: none;
    width: auto;
    margin-top: 0;
    background-color: transparent;
    border: 0;
    box-shadow: none;
  }
  .navbar-nav .open .dropdown-menu > li > a,
  .navbar-nav .open .dropdown-menu .dropdown-header {
    padding: 5px 15px 5px 25px;
  }
  .navbar-nav .open .dropdown-menu > li > a {
    line-height: 18px;
  }
  .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-nav .open .dropdown-menu > li > a:focus {
    background-image: none;
  }
}
@media (min-width: 541px) {
  .navbar-nav {
    float: left;
    margin: 0;
  }
  .navbar-nav > li {
    float: left;
  }
  .navbar-nav > li > a {
    padding-top: 6px;
    padding-bottom: 6px;
  }
}
.navbar-form {
  margin-left: 0px;
  margin-right: 0px;
  padding: 10px 0px;
  border-top: 1px solid transparent;
  border-bottom: 1px solid transparent;
  -webkit-box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  margin-top: -1px;
  margin-bottom: -1px;
}
@media (min-width: 768px) {
  .navbar-form .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .navbar-form .form-control-static {
    display: inline-block;
  }
  .navbar-form .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .navbar-form .input-group .input-group-addon,
  .navbar-form .input-group .input-group-btn,
  .navbar-form .input-group .form-control {
    width: auto;
  }
  .navbar-form .input-group > .form-control {
    width: 100%;
  }
  .navbar-form .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio,
  .navbar-form .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio label,
  .navbar-form .checkbox label {
    padding-left: 0;
  }
  .navbar-form .radio input[type="radio"],
  .navbar-form .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .navbar-form .has-feedback .form-control-feedback {
    top: 0;
  }
}
@media (max-width: 540px) {
  .navbar-form .form-group {
    margin-bottom: 5px;
  }
  .navbar-form .form-group:last-child {
    margin-bottom: 0;
  }
}
@media (min-width: 541px) {
  .navbar-form {
    width: auto;
    border: 0;
    margin-left: 0;
    margin-right: 0;
    padding-top: 0;
    padding-bottom: 0;
    -webkit-box-shadow: none;
    box-shadow: none;
  }
}
.navbar-nav > li > .dropdown-menu {
  margin-top: 0;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar-fixed-bottom .navbar-nav > li > .dropdown-menu {
  margin-bottom: 0;
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.navbar-btn {
  margin-top: -1px;
  margin-bottom: -1px;
}
.navbar-btn.btn-sm {
  margin-top: 0px;
  margin-bottom: 0px;
}
.navbar-btn.btn-xs {
  margin-top: 4px;
  margin-bottom: 4px;
}
.navbar-text {
  margin-top: 6px;
  margin-bottom: 6px;
}
@media (min-width: 541px) {
  .navbar-text {
    float: left;
    margin-left: 0px;
    margin-right: 0px;
  }
}
@media (min-width: 541px) {
  .navbar-left {
    float: left !important;
    float: left;
  }
  .navbar-right {
    float: right !important;
    float: right;
    margin-right: 0px;
  }
  .navbar-right ~ .navbar-right {
    margin-right: 0;
  }
}
.navbar-default {
  background-color: #f8f8f8;
  border-color: #e7e7e7;
}
.navbar-default .navbar-brand {
  color: #777;
}
.navbar-default .navbar-brand:hover,
.navbar-default .navbar-brand:focus {
  color: #5e5e5e;
  background-color: transparent;
}
.navbar-default .navbar-text {
  color: #777;
}
.navbar-default .navbar-nav > li > a {
  color: #777;
}
.navbar-default .navbar-nav > li > a:hover,
.navbar-default .navbar-nav > li > a:focus {
  color: #333;
  background-color: transparent;
}
.navbar-default .navbar-nav > .active > a,
.navbar-default .navbar-nav > .active > a:hover,
.navbar-default .navbar-nav > .active > a:focus {
  color: #555;
  background-color: #e7e7e7;
}
.navbar-default .navbar-nav > .disabled > a,
.navbar-default .navbar-nav > .disabled > a:hover,
.navbar-default .navbar-nav > .disabled > a:focus {
  color: #ccc;
  background-color: transparent;
}
.navbar-default .navbar-toggle {
  border-color: #ddd;
}
.navbar-default .navbar-toggle:hover,
.navbar-default .navbar-toggle:focus {
  background-color: #ddd;
}
.navbar-default .navbar-toggle .icon-bar {
  background-color: #888;
}
.navbar-default .navbar-collapse,
.navbar-default .navbar-form {
  border-color: #e7e7e7;
}
.navbar-default .navbar-nav > .open > a,
.navbar-default .navbar-nav > .open > a:hover,
.navbar-default .navbar-nav > .open > a:focus {
  background-color: #e7e7e7;
  color: #555;
}
@media (max-width: 540px) {
  .navbar-default .navbar-nav .open .dropdown-menu > li > a {
    color: #777;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #333;
    background-color: transparent;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #555;
    background-color: #e7e7e7;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #ccc;
    background-color: transparent;
  }
}
.navbar-default .navbar-link {
  color: #777;
}
.navbar-default .navbar-link:hover {
  color: #333;
}
.navbar-default .btn-link {
  color: #777;
}
.navbar-default .btn-link:hover,
.navbar-default .btn-link:focus {
  color: #333;
}
.navbar-default .btn-link[disabled]:hover,
fieldset[disabled] .navbar-default .btn-link:hover,
.navbar-default .btn-link[disabled]:focus,
fieldset[disabled] .navbar-default .btn-link:focus {
  color: #ccc;
}
.navbar-inverse {
  background-color: #222;
  border-color: #080808;
}
.navbar-inverse .navbar-brand {
  color: #9d9d9d;
}
.navbar-inverse .navbar-brand:hover,
.navbar-inverse .navbar-brand:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-text {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a:hover,
.navbar-inverse .navbar-nav > li > a:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-nav > .active > a,
.navbar-inverse .navbar-nav > .active > a:hover,
.navbar-inverse .navbar-nav > .active > a:focus {
  color: #fff;
  background-color: #080808;
}
.navbar-inverse .navbar-nav > .disabled > a,
.navbar-inverse .navbar-nav > .disabled > a:hover,
.navbar-inverse .navbar-nav > .disabled > a:focus {
  color: #444;
  background-color: transparent;
}
.navbar-inverse .navbar-toggle {
  border-color: #333;
}
.navbar-inverse .navbar-toggle:hover,
.navbar-inverse .navbar-toggle:focus {
  background-color: #333;
}
.navbar-inverse .navbar-toggle .icon-bar {
  background-color: #fff;
}
.navbar-inverse .navbar-collapse,
.navbar-inverse .navbar-form {
  border-color: #101010;
}
.navbar-inverse .navbar-nav > .open > a,
.navbar-inverse .navbar-nav > .open > a:hover,
.navbar-inverse .navbar-nav > .open > a:focus {
  background-color: #080808;
  color: #fff;
}
@media (max-width: 540px) {
  .navbar-inverse .navbar-nav .open .dropdown-menu > .dropdown-header {
    border-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu .divider {
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a {
    color: #9d9d9d;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #fff;
    background-color: transparent;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #fff;
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #444;
    background-color: transparent;
  }
}
.navbar-inverse .navbar-link {
  color: #9d9d9d;
}
.navbar-inverse .navbar-link:hover {
  color: #fff;
}
.navbar-inverse .btn-link {
  color: #9d9d9d;
}
.navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link:focus {
  color: #fff;
}
.navbar-inverse .btn-link[disabled]:hover,
fieldset[disabled] .navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link[disabled]:focus,
fieldset[disabled] .navbar-inverse .btn-link:focus {
  color: #444;
}
.breadcrumb {
  padding: 8px 15px;
  margin-bottom: 18px;
  list-style: none;
  background-color: #f5f5f5;
  border-radius: 2px;
}
.breadcrumb > li {
  display: inline-block;
}
.breadcrumb > li + li:before {
  content: "/\00a0";
  padding: 0 5px;
  color: #5e5e5e;
}
.breadcrumb > .active {
  color: #777777;
}
.pagination {
  display: inline-block;
  padding-left: 0;
  margin: 18px 0;
  border-radius: 2px;
}
.pagination > li {
  display: inline;
}
.pagination > li > a,
.pagination > li > span {
  position: relative;
  float: left;
  padding: 6px 12px;
  line-height: 1.42857143;
  text-decoration: none;
  color: #337ab7;
  background-color: #fff;
  border: 1px solid #ddd;
  margin-left: -1px;
}
.pagination > li:first-child > a,
.pagination > li:first-child > span {
  margin-left: 0;
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.pagination > li:last-child > a,
.pagination > li:last-child > span {
  border-bottom-right-radius: 2px;
  border-top-right-radius: 2px;
}
.pagination > li > a:hover,
.pagination > li > span:hover,
.pagination > li > a:focus,
.pagination > li > span:focus {
  z-index: 2;
  color: #23527c;
  background-color: #eeeeee;
  border-color: #ddd;
}
.pagination > .active > a,
.pagination > .active > span,
.pagination > .active > a:hover,
.pagination > .active > span:hover,
.pagination > .active > a:focus,
.pagination > .active > span:focus {
  z-index: 3;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
  cursor: default;
}
.pagination > .disabled > span,
.pagination > .disabled > span:hover,
.pagination > .disabled > span:focus,
.pagination > .disabled > a,
.pagination > .disabled > a:hover,
.pagination > .disabled > a:focus {
  color: #777777;
  background-color: #fff;
  border-color: #ddd;
  cursor: not-allowed;
}
.pagination-lg > li > a,
.pagination-lg > li > span {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.pagination-lg > li:first-child > a,
.pagination-lg > li:first-child > span {
  border-bottom-left-radius: 3px;
  border-top-left-radius: 3px;
}
.pagination-lg > li:last-child > a,
.pagination-lg > li:last-child > span {
  border-bottom-right-radius: 3px;
  border-top-right-radius: 3px;
}
.pagination-sm > li > a,
.pagination-sm > li > span {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.pagination-sm > li:first-child > a,
.pagination-sm > li:first-child > span {
  border-bottom-left-radius: 1px;
  border-top-left-radius: 1px;
}
.pagination-sm > li:last-child > a,
.pagination-sm > li:last-child > span {
  border-bottom-right-radius: 1px;
  border-top-right-radius: 1px;
}
.pager {
  padding-left: 0;
  margin: 18px 0;
  list-style: none;
  text-align: center;
}
.pager li {
  display: inline;
}
.pager li > a,
.pager li > span {
  display: inline-block;
  padding: 5px 14px;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 15px;
}
.pager li > a:hover,
.pager li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.pager .next > a,
.pager .next > span {
  float: right;
}
.pager .previous > a,
.pager .previous > span {
  float: left;
}
.pager .disabled > a,
.pager .disabled > a:hover,
.pager .disabled > a:focus,
.pager .disabled > span {
  color: #777777;
  background-color: #fff;
  cursor: not-allowed;
}
.label {
  display: inline;
  padding: .2em .6em .3em;
  font-size: 75%;
  font-weight: bold;
  line-height: 1;
  color: #fff;
  text-align: center;
  white-space: nowrap;
  vertical-align: baseline;
  border-radius: .25em;
}
a.label:hover,
a.label:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.label:empty {
  display: none;
}
.btn .label {
  position: relative;
  top: -1px;
}
.label-default {
  background-color: #777777;
}
.label-default[href]:hover,
.label-default[href]:focus {
  background-color: #5e5e5e;
}
.label-primary {
  background-color: #337ab7;
}
.label-primary[href]:hover,
.label-primary[href]:focus {
  background-color: #286090;
}
.label-success {
  background-color: #5cb85c;
}
.label-success[href]:hover,
.label-success[href]:focus {
  background-color: #449d44;
}
.label-info {
  background-color: #5bc0de;
}
.label-info[href]:hover,
.label-info[href]:focus {
  background-color: #31b0d5;
}
.label-warning {
  background-color: #f0ad4e;
}
.label-warning[href]:hover,
.label-warning[href]:focus {
  background-color: #ec971f;
}
.label-danger {
  background-color: #d9534f;
}
.label-danger[href]:hover,
.label-danger[href]:focus {
  background-color: #c9302c;
}
.badge {
  display: inline-block;
  min-width: 10px;
  padding: 3px 7px;
  font-size: 12px;
  font-weight: bold;
  color: #fff;
  line-height: 1;
  vertical-align: middle;
  white-space: nowrap;
  text-align: center;
  background-color: #777777;
  border-radius: 10px;
}
.badge:empty {
  display: none;
}
.btn .badge {
  position: relative;
  top: -1px;
}
.btn-xs .badge,
.btn-group-xs > .btn .badge {
  top: 0;
  padding: 1px 5px;
}
a.badge:hover,
a.badge:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.list-group-item.active > .badge,
.nav-pills > .active > a > .badge {
  color: #337ab7;
  background-color: #fff;
}
.list-group-item > .badge {
  float: right;
}
.list-group-item > .badge + .badge {
  margin-right: 5px;
}
.nav-pills > li > a > .badge {
  margin-left: 3px;
}
.jumbotron {
  padding-top: 30px;
  padding-bottom: 30px;
  margin-bottom: 30px;
  color: inherit;
  background-color: #eeeeee;
}
.jumbotron h1,
.jumbotron .h1 {
  color: inherit;
}
.jumbotron p {
  margin-bottom: 15px;
  font-size: 20px;
  font-weight: 200;
}
.jumbotron > hr {
  border-top-color: #d5d5d5;
}
.container .jumbotron,
.container-fluid .jumbotron {
  border-radius: 3px;
  padding-left: 0px;
  padding-right: 0px;
}
.jumbotron .container {
  max-width: 100%;
}
@media screen and (min-width: 768px) {
  .jumbotron {
    padding-top: 48px;
    padding-bottom: 48px;
  }
  .container .jumbotron,
  .container-fluid .jumbotron {
    padding-left: 60px;
    padding-right: 60px;
  }
  .jumbotron h1,
  .jumbotron .h1 {
    font-size: 59px;
  }
}
.thumbnail {
  display: block;
  padding: 4px;
  margin-bottom: 18px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: border 0.2s ease-in-out;
  -o-transition: border 0.2s ease-in-out;
  transition: border 0.2s ease-in-out;
}
.thumbnail > img,
.thumbnail a > img {
  margin-left: auto;
  margin-right: auto;
}
a.thumbnail:hover,
a.thumbnail:focus,
a.thumbnail.active {
  border-color: #337ab7;
}
.thumbnail .caption {
  padding: 9px;
  color: #000;
}
.alert {
  padding: 15px;
  margin-bottom: 18px;
  border: 1px solid transparent;
  border-radius: 2px;
}
.alert h4 {
  margin-top: 0;
  color: inherit;
}
.alert .alert-link {
  font-weight: bold;
}
.alert > p,
.alert > ul {
  margin-bottom: 0;
}
.alert > p + p {
  margin-top: 5px;
}
.alert-dismissable,
.alert-dismissible {
  padding-right: 35px;
}
.alert-dismissable .close,
.alert-dismissible .close {
  position: relative;
  top: -2px;
  right: -21px;
  color: inherit;
}
.alert-success {
  background-color: #dff0d8;
  border-color: #d6e9c6;
  color: #3c763d;
}
.alert-success hr {
  border-top-color: #c9e2b3;
}
.alert-success .alert-link {
  color: #2b542c;
}
.alert-info {
  background-color: #d9edf7;
  border-color: #bce8f1;
  color: #31708f;
}
.alert-info hr {
  border-top-color: #a6e1ec;
}
.alert-info .alert-link {
  color: #245269;
}
.alert-warning {
  background-color: #fcf8e3;
  border-color: #faebcc;
  color: #8a6d3b;
}
.alert-warning hr {
  border-top-color: #f7e1b5;
}
.alert-warning .alert-link {
  color: #66512c;
}
.alert-danger {
  background-color: #f2dede;
  border-color: #ebccd1;
  color: #a94442;
}
.alert-danger hr {
  border-top-color: #e4b9c0;
}
.alert-danger .alert-link {
  color: #843534;
}
@-webkit-keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
@keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
.progress {
  overflow: hidden;
  height: 18px;
  margin-bottom: 18px;
  background-color: #f5f5f5;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
  box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
}
.progress-bar {
  float: left;
  width: 0%;
  height: 100%;
  font-size: 12px;
  line-height: 18px;
  color: #fff;
  text-align: center;
  background-color: #337ab7;
  -webkit-box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  -webkit-transition: width 0.6s ease;
  -o-transition: width 0.6s ease;
  transition: width 0.6s ease;
}
.progress-striped .progress-bar,
.progress-bar-striped {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-size: 40px 40px;
}
.progress.active .progress-bar,
.progress-bar.active {
  -webkit-animation: progress-bar-stripes 2s linear infinite;
  -o-animation: progress-bar-stripes 2s linear infinite;
  animation: progress-bar-stripes 2s linear infinite;
}
.progress-bar-success {
  background-color: #5cb85c;
}
.progress-striped .progress-bar-success {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-info {
  background-color: #5bc0de;
}
.progress-striped .progress-bar-info {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-warning {
  background-color: #f0ad4e;
}
.progress-striped .progress-bar-warning {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-danger {
  background-color: #d9534f;
}
.progress-striped .progress-bar-danger {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.media {
  margin-top: 15px;
}
.media:first-child {
  margin-top: 0;
}
.media,
.media-body {
  zoom: 1;
  overflow: hidden;
}
.media-body {
  width: 10000px;
}
.media-object {
  display: block;
}
.media-object.img-thumbnail {
  max-width: none;
}
.media-right,
.media > .pull-right {
  padding-left: 10px;
}
.media-left,
.media > .pull-left {
  padding-right: 10px;
}
.media-left,
.media-right,
.media-body {
  display: table-cell;
  vertical-align: top;
}
.media-middle {
  vertical-align: middle;
}
.media-bottom {
  vertical-align: bottom;
}
.media-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.media-list {
  padding-left: 0;
  list-style: none;
}
.list-group {
  margin-bottom: 20px;
  padding-left: 0;
}
.list-group-item {
  position: relative;
  display: block;
  padding: 10px 15px;
  margin-bottom: -1px;
  background-color: #fff;
  border: 1px solid #ddd;
}
.list-group-item:first-child {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
}
.list-group-item:last-child {
  margin-bottom: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
a.list-group-item,
button.list-group-item {
  color: #555;
}
a.list-group-item .list-group-item-heading,
button.list-group-item .list-group-item-heading {
  color: #333;
}
a.list-group-item:hover,
button.list-group-item:hover,
a.list-group-item:focus,
button.list-group-item:focus {
  text-decoration: none;
  color: #555;
  background-color: #f5f5f5;
}
button.list-group-item {
  width: 100%;
  text-align: left;
}
.list-group-item.disabled,
.list-group-item.disabled:hover,
.list-group-item.disabled:focus {
  background-color: #eeeeee;
  color: #777777;
  cursor: not-allowed;
}
.list-group-item.disabled .list-group-item-heading,
.list-group-item.disabled:hover .list-group-item-heading,
.list-group-item.disabled:focus .list-group-item-heading {
  color: inherit;
}
.list-group-item.disabled .list-group-item-text,
.list-group-item.disabled:hover .list-group-item-text,
.list-group-item.disabled:focus .list-group-item-text {
  color: #777777;
}
.list-group-item.active,
.list-group-item.active:hover,
.list-group-item.active:focus {
  z-index: 2;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.list-group-item.active .list-group-item-heading,
.list-group-item.active:hover .list-group-item-heading,
.list-group-item.active:focus .list-group-item-heading,
.list-group-item.active .list-group-item-heading > small,
.list-group-item.active:hover .list-group-item-heading > small,
.list-group-item.active:focus .list-group-item-heading > small,
.list-group-item.active .list-group-item-heading > .small,
.list-group-item.active:hover .list-group-item-heading > .small,
.list-group-item.active:focus .list-group-item-heading > .small {
  color: inherit;
}
.list-group-item.active .list-group-item-text,
.list-group-item.active:hover .list-group-item-text,
.list-group-item.active:focus .list-group-item-text {
  color: #c7ddef;
}
.list-group-item-success {
  color: #3c763d;
  background-color: #dff0d8;
}
a.list-group-item-success,
button.list-group-item-success {
  color: #3c763d;
}
a.list-group-item-success .list-group-item-heading,
button.list-group-item-success .list-group-item-heading {
  color: inherit;
}
a.list-group-item-success:hover,
button.list-group-item-success:hover,
a.list-group-item-success:focus,
button.list-group-item-success:focus {
  color: #3c763d;
  background-color: #d0e9c6;
}
a.list-group-item-success.active,
button.list-group-item-success.active,
a.list-group-item-success.active:hover,
button.list-group-item-success.active:hover,
a.list-group-item-success.active:focus,
button.list-group-item-success.active:focus {
  color: #fff;
  background-color: #3c763d;
  border-color: #3c763d;
}
.list-group-item-info {
  color: #31708f;
  background-color: #d9edf7;
}
a.list-group-item-info,
button.list-group-item-info {
  color: #31708f;
}
a.list-group-item-info .list-group-item-heading,
button.list-group-item-info .list-group-item-heading {
  color: inherit;
}
a.list-group-item-info:hover,
button.list-group-item-info:hover,
a.list-group-item-info:focus,
button.list-group-item-info:focus {
  color: #31708f;
  background-color: #c4e3f3;
}
a.list-group-item-info.active,
button.list-group-item-info.active,
a.list-group-item-info.active:hover,
button.list-group-item-info.active:hover,
a.list-group-item-info.active:focus,
button.list-group-item-info.active:focus {
  color: #fff;
  background-color: #31708f;
  border-color: #31708f;
}
.list-group-item-warning {
  color: #8a6d3b;
  background-color: #fcf8e3;
}
a.list-group-item-warning,
button.list-group-item-warning {
  color: #8a6d3b;
}
a.list-group-item-warning .list-group-item-heading,
button.list-group-item-warning .list-group-item-heading {
  color: inherit;
}
a.list-group-item-warning:hover,
button.list-group-item-warning:hover,
a.list-group-item-warning:focus,
button.list-group-item-warning:focus {
  color: #8a6d3b;
  background-color: #faf2cc;
}
a.list-group-item-warning.active,
button.list-group-item-warning.active,
a.list-group-item-warning.active:hover,
button.list-group-item-warning.active:hover,
a.list-group-item-warning.active:focus,
button.list-group-item-warning.active:focus {
  color: #fff;
  background-color: #8a6d3b;
  border-color: #8a6d3b;
}
.list-group-item-danger {
  color: #a94442;
  background-color: #f2dede;
}
a.list-group-item-danger,
button.list-group-item-danger {
  color: #a94442;
}
a.list-group-item-danger .list-group-item-heading,
button.list-group-item-danger .list-group-item-heading {
  color: inherit;
}
a.list-group-item-danger:hover,
button.list-group-item-danger:hover,
a.list-group-item-danger:focus,
button.list-group-item-danger:focus {
  color: #a94442;
  background-color: #ebcccc;
}
a.list-group-item-danger.active,
button.list-group-item-danger.active,
a.list-group-item-danger.active:hover,
button.list-group-item-danger.active:hover,
a.list-group-item-danger.active:focus,
button.list-group-item-danger.active:focus {
  color: #fff;
  background-color: #a94442;
  border-color: #a94442;
}
.list-group-item-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.list-group-item-text {
  margin-bottom: 0;
  line-height: 1.3;
}
.panel {
  margin-bottom: 18px;
  background-color: #fff;
  border: 1px solid transparent;
  border-radius: 2px;
  -webkit-box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
}
.panel-body {
  padding: 15px;
}
.panel-heading {
  padding: 10px 15px;
  border-bottom: 1px solid transparent;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel-heading > .dropdown .dropdown-toggle {
  color: inherit;
}
.panel-title {
  margin-top: 0;
  margin-bottom: 0;
  font-size: 15px;
  color: inherit;
}
.panel-title > a,
.panel-title > small,
.panel-title > .small,
.panel-title > small > a,
.panel-title > .small > a {
  color: inherit;
}
.panel-footer {
  padding: 10px 15px;
  background-color: #f5f5f5;
  border-top: 1px solid #ddd;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .list-group,
.panel > .panel-collapse > .list-group {
  margin-bottom: 0;
}
.panel > .list-group .list-group-item,
.panel > .panel-collapse > .list-group .list-group-item {
  border-width: 1px 0;
  border-radius: 0;
}
.panel > .list-group:first-child .list-group-item:first-child,
.panel > .panel-collapse > .list-group:first-child .list-group-item:first-child {
  border-top: 0;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .list-group:last-child .list-group-item:last-child,
.panel > .panel-collapse > .list-group:last-child .list-group-item:last-child {
  border-bottom: 0;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .panel-heading + .panel-collapse > .list-group .list-group-item:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.panel-heading + .list-group .list-group-item:first-child {
  border-top-width: 0;
}
.list-group + .panel-footer {
  border-top-width: 0;
}
.panel > .table,
.panel > .table-responsive > .table,
.panel > .panel-collapse > .table {
  margin-bottom: 0;
}
.panel > .table caption,
.panel > .table-responsive > .table caption,
.panel > .panel-collapse > .table caption {
  padding-left: 15px;
  padding-right: 15px;
}
.panel > .table:first-child,
.panel > .table-responsive:first-child > .table:first-child {
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child {
  border-top-left-radius: 1px;
  border-top-right-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:first-child {
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:last-child {
  border-top-right-radius: 1px;
}
.panel > .table:last-child,
.panel > .table-responsive:last-child > .table:last-child {
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child {
  border-bottom-left-radius: 1px;
  border-bottom-right-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:first-child {
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:last-child {
  border-bottom-right-radius: 1px;
}
.panel > .panel-body + .table,
.panel > .panel-body + .table-responsive,
.panel > .table + .panel-body,
.panel > .table-responsive + .panel-body {
  border-top: 1px solid #ddd;
}
.panel > .table > tbody:first-child > tr:first-child th,
.panel > .table > tbody:first-child > tr:first-child td {
  border-top: 0;
}
.panel > .table-bordered,
.panel > .table-responsive > .table-bordered {
  border: 0;
}
.panel > .table-bordered > thead > tr > th:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:first-child,
.panel > .table-bordered > tbody > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:first-child,
.panel > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-bordered > thead > tr > td:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:first-child,
.panel > .table-bordered > tbody > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:first-child,
.panel > .table-bordered > tfoot > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:first-child {
  border-left: 0;
}
.panel > .table-bordered > thead > tr > th:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:last-child,
.panel > .table-bordered > tbody > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:last-child,
.panel > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-bordered > thead > tr > td:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:last-child,
.panel > .table-bordered > tbody > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:last-child,
.panel > .table-bordered > tfoot > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:last-child {
  border-right: 0;
}
.panel > .table-bordered > thead > tr:first-child > td,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > td,
.panel > .table-bordered > tbody > tr:first-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > td,
.panel > .table-bordered > thead > tr:first-child > th,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > th,
.panel > .table-bordered > tbody > tr:first-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > th {
  border-bottom: 0;
}
.panel > .table-bordered > tbody > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > td,
.panel > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-bordered > tbody > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > th,
.panel > .table-bordered > tfoot > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > th {
  border-bottom: 0;
}
.panel > .table-responsive {
  border: 0;
  margin-bottom: 0;
}
.panel-group {
  margin-bottom: 18px;
}
.panel-group .panel {
  margin-bottom: 0;
  border-radius: 2px;
}
.panel-group .panel + .panel {
  margin-top: 5px;
}
.panel-group .panel-heading {
  border-bottom: 0;
}
.panel-group .panel-heading + .panel-collapse > .panel-body,
.panel-group .panel-heading + .panel-collapse > .list-group {
  border-top: 1px solid #ddd;
}
.panel-group .panel-footer {
  border-top: 0;
}
.panel-group .panel-footer + .panel-collapse .panel-body {
  border-bottom: 1px solid #ddd;
}
.panel-default {
  border-color: #ddd;
}
.panel-default > .panel-heading {
  color: #333333;
  background-color: #f5f5f5;
  border-color: #ddd;
}
.panel-default > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ddd;
}
.panel-default > .panel-heading .badge {
  color: #f5f5f5;
  background-color: #333333;
}
.panel-default > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ddd;
}
.panel-primary {
  border-color: #337ab7;
}
.panel-primary > .panel-heading {
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.panel-primary > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #337ab7;
}
.panel-primary > .panel-heading .badge {
  color: #337ab7;
  background-color: #fff;
}
.panel-primary > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #337ab7;
}
.panel-success {
  border-color: #d6e9c6;
}
.panel-success > .panel-heading {
  color: #3c763d;
  background-color: #dff0d8;
  border-color: #d6e9c6;
}
.panel-success > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #d6e9c6;
}
.panel-success > .panel-heading .badge {
  color: #dff0d8;
  background-color: #3c763d;
}
.panel-success > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #d6e9c6;
}
.panel-info {
  border-color: #bce8f1;
}
.panel-info > .panel-heading {
  color: #31708f;
  background-color: #d9edf7;
  border-color: #bce8f1;
}
.panel-info > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #bce8f1;
}
.panel-info > .panel-heading .badge {
  color: #d9edf7;
  background-color: #31708f;
}
.panel-info > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #bce8f1;
}
.panel-warning {
  border-color: #faebcc;
}
.panel-warning > .panel-heading {
  color: #8a6d3b;
  background-color: #fcf8e3;
  border-color: #faebcc;
}
.panel-warning > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #faebcc;
}
.panel-warning > .panel-heading .badge {
  color: #fcf8e3;
  background-color: #8a6d3b;
}
.panel-warning > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #faebcc;
}
.panel-danger {
  border-color: #ebccd1;
}
.panel-danger > .panel-heading {
  color: #a94442;
  background-color: #f2dede;
  border-color: #ebccd1;
}
.panel-danger > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ebccd1;
}
.panel-danger > .panel-heading .badge {
  color: #f2dede;
  background-color: #a94442;
}
.panel-danger > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ebccd1;
}
.embed-responsive {
  position: relative;
  display: block;
  height: 0;
  padding: 0;
  overflow: hidden;
}
.embed-responsive .embed-responsive-item,
.embed-responsive iframe,
.embed-responsive embed,
.embed-responsive object,
.embed-responsive video {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  height: 100%;
  width: 100%;
  border: 0;
}
.embed-responsive-16by9 {
  padding-bottom: 56.25%;
}
.embed-responsive-4by3 {
  padding-bottom: 75%;
}
.well {
  min-height: 20px;
  padding: 19px;
  margin-bottom: 20px;
  background-color: #f5f5f5;
  border: 1px solid #e3e3e3;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
}
.well blockquote {
  border-color: #ddd;
  border-color: rgba(0, 0, 0, 0.15);
}
.well-lg {
  padding: 24px;
  border-radius: 3px;
}
.well-sm {
  padding: 9px;
  border-radius: 1px;
}
.close {
  float: right;
  font-size: 19.5px;
  font-weight: bold;
  line-height: 1;
  color: #000;
  text-shadow: 0 1px 0 #fff;
  opacity: 0.2;
  filter: alpha(opacity=20);
}
.close:hover,
.close:focus {
  color: #000;
  text-decoration: none;
  cursor: pointer;
  opacity: 0.5;
  filter: alpha(opacity=50);
}
button.close {
  padding: 0;
  cursor: pointer;
  background: transparent;
  border: 0;
  -webkit-appearance: none;
}
.modal-open {
  overflow: hidden;
}
.modal {
  display: none;
  overflow: hidden;
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1050;
  -webkit-overflow-scrolling: touch;
  outline: 0;
}
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, -25%);
  -ms-transform: translate(0, -25%);
  -o-transform: translate(0, -25%);
  transform: translate(0, -25%);
  -webkit-transition: -webkit-transform 0.3s ease-out;
  -moz-transition: -moz-transform 0.3s ease-out;
  -o-transition: -o-transform 0.3s ease-out;
  transition: transform 0.3s ease-out;
}
.modal.in .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
.modal-open .modal {
  overflow-x: hidden;
  overflow-y: auto;
}
.modal-dialog {
  position: relative;
  width: auto;
  margin: 10px;
}
.modal-content {
  position: relative;
  background-color: #fff;
  border: 1px solid #999;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  background-clip: padding-box;
  outline: 0;
}
.modal-backdrop {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1040;
  background-color: #000;
}
.modal-backdrop.fade {
  opacity: 0;
  filter: alpha(opacity=0);
}
.modal-backdrop.in {
  opacity: 0.5;
  filter: alpha(opacity=50);
}
.modal-header {
  padding: 15px;
  border-bottom: 1px solid #e5e5e5;
}
.modal-header .close {
  margin-top: -2px;
}
.modal-title {
  margin: 0;
  line-height: 1.42857143;
}
.modal-body {
  position: relative;
  padding: 15px;
}
.modal-footer {
  padding: 15px;
  text-align: right;
  border-top: 1px solid #e5e5e5;
}
.modal-footer .btn + .btn {
  margin-left: 5px;
  margin-bottom: 0;
}
.modal-footer .btn-group .btn + .btn {
  margin-left: -1px;
}
.modal-footer .btn-block + .btn-block {
  margin-left: 0;
}
.modal-scrollbar-measure {
  position: absolute;
  top: -9999px;
  width: 50px;
  height: 50px;
  overflow: scroll;
}
@media (min-width: 768px) {
  .modal-dialog {
    width: 600px;
    margin: 30px auto;
  }
  .modal-content {
    -webkit-box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
  }
  .modal-sm {
    width: 300px;
  }
}
@media (min-width: 992px) {
  .modal-lg {
    width: 900px;
  }
}
.tooltip {
  position: absolute;
  z-index: 1070;
  display: block;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 12px;
  opacity: 0;
  filter: alpha(opacity=0);
}
.tooltip.in {
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.tooltip.top {
  margin-top: -3px;
  padding: 5px 0;
}
.tooltip.right {
  margin-left: 3px;
  padding: 0 5px;
}
.tooltip.bottom {
  margin-top: 3px;
  padding: 5px 0;
}
.tooltip.left {
  margin-left: -3px;
  padding: 0 5px;
}
.tooltip-inner {
  max-width: 200px;
  padding: 3px 8px;
  color: #fff;
  text-align: center;
  background-color: #000;
  border-radius: 2px;
}
.tooltip-arrow {
  position: absolute;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.tooltip.top .tooltip-arrow {
  bottom: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-left .tooltip-arrow {
  bottom: 0;
  right: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-right .tooltip-arrow {
  bottom: 0;
  left: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.right .tooltip-arrow {
  top: 50%;
  left: 0;
  margin-top: -5px;
  border-width: 5px 5px 5px 0;
  border-right-color: #000;
}
.tooltip.left .tooltip-arrow {
  top: 50%;
  right: 0;
  margin-top: -5px;
  border-width: 5px 0 5px 5px;
  border-left-color: #000;
}
.tooltip.bottom .tooltip-arrow {
  top: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-left .tooltip-arrow {
  top: 0;
  right: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-right .tooltip-arrow {
  top: 0;
  left: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.popover {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1060;
  display: none;
  max-width: 276px;
  padding: 1px;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 13px;
  background-color: #fff;
  background-clip: padding-box;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
}
.popover.top {
  margin-top: -10px;
}
.popover.right {
  margin-left: 10px;
}
.popover.bottom {
  margin-top: 10px;
}
.popover.left {
  margin-left: -10px;
}
.popover-title {
  margin: 0;
  padding: 8px 14px;
  font-size: 13px;
  background-color: #f7f7f7;
  border-bottom: 1px solid #ebebeb;
  border-radius: 2px 2px 0 0;
}
.popover-content {
  padding: 9px 14px;
}
.popover > .arrow,
.popover > .arrow:after {
  position: absolute;
  display: block;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.popover > .arrow {
  border-width: 11px;
}
.popover > .arrow:after {
  border-width: 10px;
  content: "";
}
.popover.top > .arrow {
  left: 50%;
  margin-left: -11px;
  border-bottom-width: 0;
  border-top-color: #999999;
  border-top-color: rgba(0, 0, 0, 0.25);
  bottom: -11px;
}
.popover.top > .arrow:after {
  content: " ";
  bottom: 1px;
  margin-left: -10px;
  border-bottom-width: 0;
  border-top-color: #fff;
}
.popover.right > .arrow {
  top: 50%;
  left: -11px;
  margin-top: -11px;
  border-left-width: 0;
  border-right-color: #999999;
  border-right-color: rgba(0, 0, 0, 0.25);
}
.popover.right > .arrow:after {
  content: " ";
  left: 1px;
  bottom: -10px;
  border-left-width: 0;
  border-right-color: #fff;
}
.popover.bottom > .arrow {
  left: 50%;
  margin-left: -11px;
  border-top-width: 0;
  border-bottom-color: #999999;
  border-bottom-color: rgba(0, 0, 0, 0.25);
  top: -11px;
}
.popover.bottom > .arrow:after {
  content: " ";
  top: 1px;
  margin-left: -10px;
  border-top-width: 0;
  border-bottom-color: #fff;
}
.popover.left > .arrow {
  top: 50%;
  right: -11px;
  margin-top: -11px;
  border-right-width: 0;
  border-left-color: #999999;
  border-left-color: rgba(0, 0, 0, 0.25);
}
.popover.left > .arrow:after {
  content: " ";
  right: 1px;
  border-right-width: 0;
  border-left-color: #fff;
  bottom: -10px;
}
.carousel {
  position: relative;
}
.carousel-inner {
  position: relative;
  overflow: hidden;
  width: 100%;
}
.carousel-inner > .item {
  display: none;
  position: relative;
  -webkit-transition: 0.6s ease-in-out left;
  -o-transition: 0.6s ease-in-out left;
  transition: 0.6s ease-in-out left;
}
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  line-height: 1;
}
@media all and (transform-3d), (-webkit-transform-3d) {
  .carousel-inner > .item {
    -webkit-transition: -webkit-transform 0.6s ease-in-out;
    -moz-transition: -moz-transform 0.6s ease-in-out;
    -o-transition: -o-transform 0.6s ease-in-out;
    transition: transform 0.6s ease-in-out;
    -webkit-backface-visibility: hidden;
    -moz-backface-visibility: hidden;
    backface-visibility: hidden;
    -webkit-perspective: 1000px;
    -moz-perspective: 1000px;
    perspective: 1000px;
  }
  .carousel-inner > .item.next,
  .carousel-inner > .item.active.right {
    -webkit-transform: translate3d(100%, 0, 0);
    transform: translate3d(100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.prev,
  .carousel-inner > .item.active.left {
    -webkit-transform: translate3d(-100%, 0, 0);
    transform: translate3d(-100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.next.left,
  .carousel-inner > .item.prev.right,
  .carousel-inner > .item.active {
    -webkit-transform: translate3d(0, 0, 0);
    transform: translate3d(0, 0, 0);
    left: 0;
  }
}
.carousel-inner > .active,
.carousel-inner > .next,
.carousel-inner > .prev {
  display: block;
}
.carousel-inner > .active {
  left: 0;
}
.carousel-inner > .next,
.carousel-inner > .prev {
  position: absolute;
  top: 0;
  width: 100%;
}
.carousel-inner > .next {
  left: 100%;
}
.carousel-inner > .prev {
  left: -100%;
}
.carousel-inner > .next.left,
.carousel-inner > .prev.right {
  left: 0;
}
.carousel-inner > .active.left {
  left: -100%;
}
.carousel-inner > .active.right {
  left: 100%;
}
.carousel-control {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  width: 15%;
  opacity: 0.5;
  filter: alpha(opacity=50);
  font-size: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
  background-color: rgba(0, 0, 0, 0);
}
.carousel-control.left {
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#80000000', endColorstr='#00000000', GradientType=1);
}
.carousel-control.right {
  left: auto;
  right: 0;
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#00000000', endColorstr='#80000000', GradientType=1);
}
.carousel-control:hover,
.carousel-control:focus {
  outline: 0;
  color: #fff;
  text-decoration: none;
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.carousel-control .icon-prev,
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-left,
.carousel-control .glyphicon-chevron-right {
  position: absolute;
  top: 50%;
  margin-top: -10px;
  z-index: 5;
  display: inline-block;
}
.carousel-control .icon-prev,
.carousel-control .glyphicon-chevron-left {
  left: 50%;
  margin-left: -10px;
}
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-right {
  right: 50%;
  margin-right: -10px;
}
.carousel-control .icon-prev,
.carousel-control .icon-next {
  width: 20px;
  height: 20px;
  line-height: 1;
  font-family: serif;
}
.carousel-control .icon-prev:before {
  content: '\2039';
}
.carousel-control .icon-next:before {
  content: '\203a';
}
.carousel-indicators {
  position: absolute;
  bottom: 10px;
  left: 50%;
  z-index: 15;
  width: 60%;
  margin-left: -30%;
  padding-left: 0;
  list-style: none;
  text-align: center;
}
.carousel-indicators li {
  display: inline-block;
  width: 10px;
  height: 10px;
  margin: 1px;
  text-indent: -999px;
  border: 1px solid #fff;
  border-radius: 10px;
  cursor: pointer;
  background-color: #000 \9;
  background-color: rgba(0, 0, 0, 0);
}
.carousel-indicators .active {
  margin: 0;
  width: 12px;
  height: 12px;
  background-color: #fff;
}
.carousel-caption {
  position: absolute;
  left: 15%;
  right: 15%;
  bottom: 20px;
  z-index: 10;
  padding-top: 20px;
  padding-bottom: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
}
.carousel-caption .btn {
  text-shadow: none;
}
@media screen and (min-width: 768px) {
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-prev,
  .carousel-control .icon-next {
    width: 30px;
    height: 30px;
    margin-top: -10px;
    font-size: 30px;
  }
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .icon-prev {
    margin-left: -10px;
  }
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-next {
    margin-right: -10px;
  }
  .carousel-caption {
    left: 20%;
    right: 20%;
    padding-bottom: 30px;
  }
  .carousel-indicators {
    bottom: 20px;
  }
}
.clearfix:before,
.clearfix:after,
.dl-horizontal dd:before,
.dl-horizontal dd:after,
.container:before,
.container:after,
.container-fluid:before,
.container-fluid:after,
.row:before,
.row:after,
.form-horizontal .form-group:before,
.form-horizontal .form-group:after,
.btn-toolbar:before,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:before,
.btn-group-vertical > .btn-group:after,
.nav:before,
.nav:after,
.navbar:before,
.navbar:after,
.navbar-header:before,
.navbar-header:after,
.navbar-collapse:before,
.navbar-collapse:after,
.pager:before,
.pager:after,
.panel-body:before,
.panel-body:after,
.modal-header:before,
.modal-header:after,
.modal-footer:before,
.modal-footer:after,
.item_buttons:before,
.item_buttons:after {
  content: " ";
  display: table;
}
.clearfix:after,
.dl-horizontal dd:after,
.container:after,
.container-fluid:after,
.row:after,
.form-horizontal .form-group:after,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:after,
.nav:after,
.navbar:after,
.navbar-header:after,
.navbar-collapse:after,
.pager:after,
.panel-body:after,
.modal-header:after,
.modal-footer:after,
.item_buttons:after {
  clear: both;
}
.center-block {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.pull-right {
  float: right !important;
}
.pull-left {
  float: left !important;
}
.hide {
  display: none !important;
}
.show {
  display: block !important;
}
.invisible {
  visibility: hidden;
}
.text-hide {
  font: 0/0 a;
  color: transparent;
  text-shadow: none;
  background-color: transparent;
  border: 0;
}
.hidden {
  display: none !important;
}
.affix {
  position: fixed;
}
@-ms-viewport {
  width: device-width;
}
.visible-xs,
.visible-sm,
.visible-md,
.visible-lg {
  display: none !important;
}
.visible-xs-block,
.visible-xs-inline,
.visible-xs-inline-block,
.visible-sm-block,
.visible-sm-inline,
.visible-sm-inline-block,
.visible-md-block,
.visible-md-inline,
.visible-md-inline-block,
.visible-lg-block,
.visible-lg-inline,
.visible-lg-inline-block {
  display: none !important;
}
@media (max-width: 767px) {
  .visible-xs {
    display: block !important;
  }
  table.visible-xs {
    display: table !important;
  }
  tr.visible-xs {
    display: table-row !important;
  }
  th.visible-xs,
  td.visible-xs {
    display: table-cell !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-block {
    display: block !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline {
    display: inline !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm {
    display: block !important;
  }
  table.visible-sm {
    display: table !important;
  }
  tr.visible-sm {
    display: table-row !important;
  }
  th.visible-sm,
  td.visible-sm {
    display: table-cell !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-block {
    display: block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline {
    display: inline !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md {
    display: block !important;
  }
  table.visible-md {
    display: table !important;
  }
  tr.visible-md {
    display: table-row !important;
  }
  th.visible-md,
  td.visible-md {
    display: table-cell !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-block {
    display: block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline {
    display: inline !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg {
    display: block !important;
  }
  table.visible-lg {
    display: table !important;
  }
  tr.visible-lg {
    display: table-row !important;
  }
  th.visible-lg,
  td.visible-lg {
    display: table-cell !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-block {
    display: block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline {
    display: inline !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline-block {
    display: inline-block !important;
  }
}
@media (max-width: 767px) {
  .hidden-xs {
    display: none !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .hidden-sm {
    display: none !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .hidden-md {
    display: none !important;
  }
}
@media (min-width: 1200px) {
  .hidden-lg {
    display: none !important;
  }
}
.visible-print {
  display: none !important;
}
@media print {
  .visible-print {
    display: block !important;
  }
  table.visible-print {
    display: table !important;
  }
  tr.visible-print {
    display: table-row !important;
  }
  th.visible-print,
  td.visible-print {
    display: table-cell !important;
  }
}
.visible-print-block {
  display: none !important;
}
@media print {
  .visible-print-block {
    display: block !important;
  }
}
.visible-print-inline {
  display: none !important;
}
@media print {
  .visible-print-inline {
    display: inline !important;
  }
}
.visible-print-inline-block {
  display: none !important;
}
@media print {
  .visible-print-inline-block {
    display: inline-block !important;
  }
}
@media print {
  .hidden-print {
    display: none !important;
  }
}
/*!
*
* Font Awesome
*
*/
/*!
 *  Font Awesome 4.7.0 by @davegandy - http://fontawesome.io - @fontawesome
 *  License - http://fontawesome.io/license (Font: SIL OFL 1.1, CSS: MIT License)
 */
/* FONT PATH
 * -------------------------- */
@font-face {
  font-family: 'FontAwesome';
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?v=4.7.0');
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?#iefix&v=4.7.0') format('embedded-opentype'), url('../components/font-awesome/fonts/fontawesome-webfont.woff2?v=4.7.0') format('woff2'), url('../components/font-awesome/fonts/fontawesome-webfont.woff?v=4.7.0') format('woff'), url('../components/font-awesome/fonts/fontawesome-webfont.ttf?v=4.7.0') format('truetype'), url('../components/font-awesome/fonts/fontawesome-webfont.svg?v=4.7.0#fontawesomeregular') format('svg');
  font-weight: normal;
  font-style: normal;
}
.fa {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
/* makes the font 33% larger relative to the icon container */
.fa-lg {
  font-size: 1.33333333em;
  line-height: 0.75em;
  vertical-align: -15%;
}
.fa-2x {
  font-size: 2em;
}
.fa-3x {
  font-size: 3em;
}
.fa-4x {
  font-size: 4em;
}
.fa-5x {
  font-size: 5em;
}
.fa-fw {
  width: 1.28571429em;
  text-align: center;
}
.fa-ul {
  padding-left: 0;
  margin-left: 2.14285714em;
  list-style-type: none;
}
.fa-ul > li {
  position: relative;
}
.fa-li {
  position: absolute;
  left: -2.14285714em;
  width: 2.14285714em;
  top: 0.14285714em;
  text-align: center;
}
.fa-li.fa-lg {
  left: -1.85714286em;
}
.fa-border {
  padding: .2em .25em .15em;
  border: solid 0.08em #eee;
  border-radius: .1em;
}
.fa-pull-left {
  float: left;
}
.fa-pull-right {
  float: right;
}
.fa.fa-pull-left {
  margin-right: .3em;
}
.fa.fa-pull-right {
  margin-left: .3em;
}
/* Deprecated as of 4.4.0 */
.pull-right {
  float: right;
}
.pull-left {
  float: left;
}
.fa.pull-left {
  margin-right: .3em;
}
.fa.pull-right {
  margin-left: .3em;
}
.fa-spin {
  -webkit-animation: fa-spin 2s infinite linear;
  animation: fa-spin 2s infinite linear;
}
.fa-pulse {
  -webkit-animation: fa-spin 1s infinite steps(8);
  animation: fa-spin 1s infinite steps(8);
}
@-webkit-keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
@keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
.fa-rotate-90 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=1)";
  -webkit-transform: rotate(90deg);
  -ms-transform: rotate(90deg);
  transform: rotate(90deg);
}
.fa-rotate-180 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=2)";
  -webkit-transform: rotate(180deg);
  -ms-transform: rotate(180deg);
  transform: rotate(180deg);
}
.fa-rotate-270 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=3)";
  -webkit-transform: rotate(270deg);
  -ms-transform: rotate(270deg);
  transform: rotate(270deg);
}
.fa-flip-horizontal {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=0, mirror=1)";
  -webkit-transform: scale(-1, 1);
  -ms-transform: scale(-1, 1);
  transform: scale(-1, 1);
}
.fa-flip-vertical {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=2, mirror=1)";
  -webkit-transform: scale(1, -1);
  -ms-transform: scale(1, -1);
  transform: scale(1, -1);
}
:root .fa-rotate-90,
:root .fa-rotate-180,
:root .fa-rotate-270,
:root .fa-flip-horizontal,
:root .fa-flip-vertical {
  filter: none;
}
.fa-stack {
  position: relative;
  display: inline-block;
  width: 2em;
  height: 2em;
  line-height: 2em;
  vertical-align: middle;
}
.fa-stack-1x,
.fa-stack-2x {
  position: absolute;
  left: 0;
  width: 100%;
  text-align: center;
}
.fa-stack-1x {
  line-height: inherit;
}
.fa-stack-2x {
  font-size: 2em;
}
.fa-inverse {
  color: #fff;
}
/* Font Awesome uses the Unicode Private Use Area (PUA) to ensure screen
   readers do not read off random characters that represent icons */
.fa-glass:before {
  content: "\f000";
}
.fa-music:before {
  content: "\f001";
}
.fa-search:before {
  content: "\f002";
}
.fa-envelope-o:before {
  content: "\f003";
}
.fa-heart:before {
  content: "\f004";
}
.fa-star:before {
  content: "\f005";
}
.fa-star-o:before {
  content: "\f006";
}
.fa-user:before {
  content: "\f007";
}
.fa-film:before {
  content: "\f008";
}
.fa-th-large:before {
  content: "\f009";
}
.fa-th:before {
  content: "\f00a";
}
.fa-th-list:before {
  content: "\f00b";
}
.fa-check:before {
  content: "\f00c";
}
.fa-remove:before,
.fa-close:before,
.fa-times:before {
  content: "\f00d";
}
.fa-search-plus:before {
  content: "\f00e";
}
.fa-search-minus:before {
  content: "\f010";
}
.fa-power-off:before {
  content: "\f011";
}
.fa-signal:before {
  content: "\f012";
}
.fa-gear:before,
.fa-cog:before {
  content: "\f013";
}
.fa-trash-o:before {
  content: "\f014";
}
.fa-home:before {
  content: "\f015";
}
.fa-file-o:before {
  content: "\f016";
}
.fa-clock-o:before {
  content: "\f017";
}
.fa-road:before {
  content: "\f018";
}
.fa-download:before {
  content: "\f019";
}
.fa-arrow-circle-o-down:before {
  content: "\f01a";
}
.fa-arrow-circle-o-up:before {
  content: "\f01b";
}
.fa-inbox:before {
  content: "\f01c";
}
.fa-play-circle-o:before {
  content: "\f01d";
}
.fa-rotate-right:before,
.fa-repeat:before {
  content: "\f01e";
}
.fa-refresh:before {
  content: "\f021";
}
.fa-list-alt:before {
  content: "\f022";
}
.fa-lock:before {
  content: "\f023";
}
.fa-flag:before {
  content: "\f024";
}
.fa-headphones:before {
  content: "\f025";
}
.fa-volume-off:before {
  content: "\f026";
}
.fa-volume-down:before {
  content: "\f027";
}
.fa-volume-up:before {
  content: "\f028";
}
.fa-qrcode:before {
  content: "\f029";
}
.fa-barcode:before {
  content: "\f02a";
}
.fa-tag:before {
  content: "\f02b";
}
.fa-tags:before {
  content: "\f02c";
}
.fa-book:before {
  content: "\f02d";
}
.fa-bookmark:before {
  content: "\f02e";
}
.fa-print:before {
  content: "\f02f";
}
.fa-camera:before {
  content: "\f030";
}
.fa-font:before {
  content: "\f031";
}
.fa-bold:before {
  content: "\f032";
}
.fa-italic:before {
  content: "\f033";
}
.fa-text-height:before {
  content: "\f034";
}
.fa-text-width:before {
  content: "\f035";
}
.fa-align-left:before {
  content: "\f036";
}
.fa-align-center:before {
  content: "\f037";
}
.fa-align-right:before {
  content: "\f038";
}
.fa-align-justify:before {
  content: "\f039";
}
.fa-list:before {
  content: "\f03a";
}
.fa-dedent:before,
.fa-outdent:before {
  content: "\f03b";
}
.fa-indent:before {
  content: "\f03c";
}
.fa-video-camera:before {
  content: "\f03d";
}
.fa-photo:before,
.fa-image:before,
.fa-picture-o:before {
  content: "\f03e";
}
.fa-pencil:before {
  content: "\f040";
}
.fa-map-marker:before {
  content: "\f041";
}
.fa-adjust:before {
  content: "\f042";
}
.fa-tint:before {
  content: "\f043";
}
.fa-edit:before,
.fa-pencil-square-o:before {
  content: "\f044";
}
.fa-share-square-o:before {
  content: "\f045";
}
.fa-check-square-o:before {
  content: "\f046";
}
.fa-arrows:before {
  content: "\f047";
}
.fa-step-backward:before {
  content: "\f048";
}
.fa-fast-backward:before {
  content: "\f049";
}
.fa-backward:before {
  content: "\f04a";
}
.fa-play:before {
  content: "\f04b";
}
.fa-pause:before {
  content: "\f04c";
}
.fa-stop:before {
  content: "\f04d";
}
.fa-forward:before {
  content: "\f04e";
}
.fa-fast-forward:before {
  content: "\f050";
}
.fa-step-forward:before {
  content: "\f051";
}
.fa-eject:before {
  content: "\f052";
}
.fa-chevron-left:before {
  content: "\f053";
}
.fa-chevron-right:before {
  content: "\f054";
}
.fa-plus-circle:before {
  content: "\f055";
}
.fa-minus-circle:before {
  content: "\f056";
}
.fa-times-circle:before {
  content: "\f057";
}
.fa-check-circle:before {
  content: "\f058";
}
.fa-question-circle:before {
  content: "\f059";
}
.fa-info-circle:before {
  content: "\f05a";
}
.fa-crosshairs:before {
  content: "\f05b";
}
.fa-times-circle-o:before {
  content: "\f05c";
}
.fa-check-circle-o:before {
  content: "\f05d";
}
.fa-ban:before {
  content: "\f05e";
}
.fa-arrow-left:before {
  content: "\f060";
}
.fa-arrow-right:before {
  content: "\f061";
}
.fa-arrow-up:before {
  content: "\f062";
}
.fa-arrow-down:before {
  content: "\f063";
}
.fa-mail-forward:before,
.fa-share:before {
  content: "\f064";
}
.fa-expand:before {
  content: "\f065";
}
.fa-compress:before {
  content: "\f066";
}
.fa-plus:before {
  content: "\f067";
}
.fa-minus:before {
  content: "\f068";
}
.fa-asterisk:before {
  content: "\f069";
}
.fa-exclamation-circle:before {
  content: "\f06a";
}
.fa-gift:before {
  content: "\f06b";
}
.fa-leaf:before {
  content: "\f06c";
}
.fa-fire:before {
  content: "\f06d";
}
.fa-eye:before {
  content: "\f06e";
}
.fa-eye-slash:before {
  content: "\f070";
}
.fa-warning:before,
.fa-exclamation-triangle:before {
  content: "\f071";
}
.fa-plane:before {
  content: "\f072";
}
.fa-calendar:before {
  content: "\f073";
}
.fa-random:before {
  content: "\f074";
}
.fa-comment:before {
  content: "\f075";
}
.fa-magnet:before {
  content: "\f076";
}
.fa-chevron-up:before {
  content: "\f077";
}
.fa-chevron-down:before {
  content: "\f078";
}
.fa-retweet:before {
  content: "\f079";
}
.fa-shopping-cart:before {
  content: "\f07a";
}
.fa-folder:before {
  content: "\f07b";
}
.fa-folder-open:before {
  content: "\f07c";
}
.fa-arrows-v:before {
  content: "\f07d";
}
.fa-arrows-h:before {
  content: "\f07e";
}
.fa-bar-chart-o:before,
.fa-bar-chart:before {
  content: "\f080";
}
.fa-twitter-square:before {
  content: "\f081";
}
.fa-facebook-square:before {
  content: "\f082";
}
.fa-camera-retro:before {
  content: "\f083";
}
.fa-key:before {
  content: "\f084";
}
.fa-gears:before,
.fa-cogs:before {
  content: "\f085";
}
.fa-comments:before {
  content: "\f086";
}
.fa-thumbs-o-up:before {
  content: "\f087";
}
.fa-thumbs-o-down:before {
  content: "\f088";
}
.fa-star-half:before {
  content: "\f089";
}
.fa-heart-o:before {
  content: "\f08a";
}
.fa-sign-out:before {
  content: "\f08b";
}
.fa-linkedin-square:before {
  content: "\f08c";
}
.fa-thumb-tack:before {
  content: "\f08d";
}
.fa-external-link:before {
  content: "\f08e";
}
.fa-sign-in:before {
  content: "\f090";
}
.fa-trophy:before {
  content: "\f091";
}
.fa-github-square:before {
  content: "\f092";
}
.fa-upload:before {
  content: "\f093";
}
.fa-lemon-o:before {
  content: "\f094";
}
.fa-phone:before {
  content: "\f095";
}
.fa-square-o:before {
  content: "\f096";
}
.fa-bookmark-o:before {
  content: "\f097";
}
.fa-phone-square:before {
  content: "\f098";
}
.fa-twitter:before {
  content: "\f099";
}
.fa-facebook-f:before,
.fa-facebook:before {
  content: "\f09a";
}
.fa-github:before {
  content: "\f09b";
}
.fa-unlock:before {
  content: "\f09c";
}
.fa-credit-card:before {
  content: "\f09d";
}
.fa-feed:before,
.fa-rss:before {
  content: "\f09e";
}
.fa-hdd-o:before {
  content: "\f0a0";
}
.fa-bullhorn:before {
  content: "\f0a1";
}
.fa-bell:before {
  content: "\f0f3";
}
.fa-certificate:before {
  content: "\f0a3";
}
.fa-hand-o-right:before {
  content: "\f0a4";
}
.fa-hand-o-left:before {
  content: "\f0a5";
}
.fa-hand-o-up:before {
  content: "\f0a6";
}
.fa-hand-o-down:before {
  content: "\f0a7";
}
.fa-arrow-circle-left:before {
  content: "\f0a8";
}
.fa-arrow-circle-right:before {
  content: "\f0a9";
}
.fa-arrow-circle-up:before {
  content: "\f0aa";
}
.fa-arrow-circle-down:before {
  content: "\f0ab";
}
.fa-globe:before {
  content: "\f0ac";
}
.fa-wrench:before {
  content: "\f0ad";
}
.fa-tasks:before {
  content: "\f0ae";
}
.fa-filter:before {
  content: "\f0b0";
}
.fa-briefcase:before {
  content: "\f0b1";
}
.fa-arrows-alt:before {
  content: "\f0b2";
}
.fa-group:before,
.fa-users:before {
  content: "\f0c0";
}
.fa-chain:before,
.fa-link:before {
  content: "\f0c1";
}
.fa-cloud:before {
  content: "\f0c2";
}
.fa-flask:before {
  content: "\f0c3";
}
.fa-cut:before,
.fa-scissors:before {
  content: "\f0c4";
}
.fa-copy:before,
.fa-files-o:before {
  content: "\f0c5";
}
.fa-paperclip:before {
  content: "\f0c6";
}
.fa-save:before,
.fa-floppy-o:before {
  content: "\f0c7";
}
.fa-square:before {
  content: "\f0c8";
}
.fa-navicon:before,
.fa-reorder:before,
.fa-bars:before {
  content: "\f0c9";
}
.fa-list-ul:before {
  content: "\f0ca";
}
.fa-list-ol:before {
  content: "\f0cb";
}
.fa-strikethrough:before {
  content: "\f0cc";
}
.fa-underline:before {
  content: "\f0cd";
}
.fa-table:before {
  content: "\f0ce";
}
.fa-magic:before {
  content: "\f0d0";
}
.fa-truck:before {
  content: "\f0d1";
}
.fa-pinterest:before {
  content: "\f0d2";
}
.fa-pinterest-square:before {
  content: "\f0d3";
}
.fa-google-plus-square:before {
  content: "\f0d4";
}
.fa-google-plus:before {
  content: "\f0d5";
}
.fa-money:before {
  content: "\f0d6";
}
.fa-caret-down:before {
  content: "\f0d7";
}
.fa-caret-up:before {
  content: "\f0d8";
}
.fa-caret-left:before {
  content: "\f0d9";
}
.fa-caret-right:before {
  content: "\f0da";
}
.fa-columns:before {
  content: "\f0db";
}
.fa-unsorted:before,
.fa-sort:before {
  content: "\f0dc";
}
.fa-sort-down:before,
.fa-sort-desc:before {
  content: "\f0dd";
}
.fa-sort-up:before,
.fa-sort-asc:before {
  content: "\f0de";
}
.fa-envelope:before {
  content: "\f0e0";
}
.fa-linkedin:before {
  content: "\f0e1";
}
.fa-rotate-left:before,
.fa-undo:before {
  content: "\f0e2";
}
.fa-legal:before,
.fa-gavel:before {
  content: "\f0e3";
}
.fa-dashboard:before,
.fa-tachometer:before {
  content: "\f0e4";
}
.fa-comment-o:before {
  content: "\f0e5";
}
.fa-comments-o:before {
  content: "\f0e6";
}
.fa-flash:before,
.fa-bolt:before {
  content: "\f0e7";
}
.fa-sitemap:before {
  content: "\f0e8";
}
.fa-umbrella:before {
  content: "\f0e9";
}
.fa-paste:before,
.fa-clipboard:before {
  content: "\f0ea";
}
.fa-lightbulb-o:before {
  content: "\f0eb";
}
.fa-exchange:before {
  content: "\f0ec";
}
.fa-cloud-download:before {
  content: "\f0ed";
}
.fa-cloud-upload:before {
  content: "\f0ee";
}
.fa-user-md:before {
  content: "\f0f0";
}
.fa-stethoscope:before {
  content: "\f0f1";
}
.fa-suitcase:before {
  content: "\f0f2";
}
.fa-bell-o:before {
  content: "\f0a2";
}
.fa-coffee:before {
  content: "\f0f4";
}
.fa-cutlery:before {
  content: "\f0f5";
}
.fa-file-text-o:before {
  content: "\f0f6";
}
.fa-building-o:before {
  content: "\f0f7";
}
.fa-hospital-o:before {
  content: "\f0f8";
}
.fa-ambulance:before {
  content: "\f0f9";
}
.fa-medkit:before {
  content: "\f0fa";
}
.fa-fighter-jet:before {
  content: "\f0fb";
}
.fa-beer:before {
  content: "\f0fc";
}
.fa-h-square:before {
  content: "\f0fd";
}
.fa-plus-square:before {
  content: "\f0fe";
}
.fa-angle-double-left:before {
  content: "\f100";
}
.fa-angle-double-right:before {
  content: "\f101";
}
.fa-angle-double-up:before {
  content: "\f102";
}
.fa-angle-double-down:before {
  content: "\f103";
}
.fa-angle-left:before {
  content: "\f104";
}
.fa-angle-right:before {
  content: "\f105";
}
.fa-angle-up:before {
  content: "\f106";
}
.fa-angle-down:before {
  content: "\f107";
}
.fa-desktop:before {
  content: "\f108";
}
.fa-laptop:before {
  content: "\f109";
}
.fa-tablet:before {
  content: "\f10a";
}
.fa-mobile-phone:before,
.fa-mobile:before {
  content: "\f10b";
}
.fa-circle-o:before {
  content: "\f10c";
}
.fa-quote-left:before {
  content: "\f10d";
}
.fa-quote-right:before {
  content: "\f10e";
}
.fa-spinner:before {
  content: "\f110";
}
.fa-circle:before {
  content: "\f111";
}
.fa-mail-reply:before,
.fa-reply:before {
  content: "\f112";
}
.fa-github-alt:before {
  content: "\f113";
}
.fa-folder-o:before {
  content: "\f114";
}
.fa-folder-open-o:before {
  content: "\f115";
}
.fa-smile-o:before {
  content: "\f118";
}
.fa-frown-o:before {
  content: "\f119";
}
.fa-meh-o:before {
  content: "\f11a";
}
.fa-gamepad:before {
  content: "\f11b";
}
.fa-keyboard-o:before {
  content: "\f11c";
}
.fa-flag-o:before {
  content: "\f11d";
}
.fa-flag-checkered:before {
  content: "\f11e";
}
.fa-terminal:before {
  content: "\f120";
}
.fa-code:before {
  content: "\f121";
}
.fa-mail-reply-all:before,
.fa-reply-all:before {
  content: "\f122";
}
.fa-star-half-empty:before,
.fa-star-half-full:before,
.fa-star-half-o:before {
  content: "\f123";
}
.fa-location-arrow:before {
  content: "\f124";
}
.fa-crop:before {
  content: "\f125";
}
.fa-code-fork:before {
  content: "\f126";
}
.fa-unlink:before,
.fa-chain-broken:before {
  content: "\f127";
}
.fa-question:before {
  content: "\f128";
}
.fa-info:before {
  content: "\f129";
}
.fa-exclamation:before {
  content: "\f12a";
}
.fa-superscript:before {
  content: "\f12b";
}
.fa-subscript:before {
  content: "\f12c";
}
.fa-eraser:before {
  content: "\f12d";
}
.fa-puzzle-piece:before {
  content: "\f12e";
}
.fa-microphone:before {
  content: "\f130";
}
.fa-microphone-slash:before {
  content: "\f131";
}
.fa-shield:before {
  content: "\f132";
}
.fa-calendar-o:before {
  content: "\f133";
}
.fa-fire-extinguisher:before {
  content: "\f134";
}
.fa-rocket:before {
  content: "\f135";
}
.fa-maxcdn:before {
  content: "\f136";
}
.fa-chevron-circle-left:before {
  content: "\f137";
}
.fa-chevron-circle-right:before {
  content: "\f138";
}
.fa-chevron-circle-up:before {
  content: "\f139";
}
.fa-chevron-circle-down:before {
  content: "\f13a";
}
.fa-html5:before {
  content: "\f13b";
}
.fa-css3:before {
  content: "\f13c";
}
.fa-anchor:before {
  content: "\f13d";
}
.fa-unlock-alt:before {
  content: "\f13e";
}
.fa-bullseye:before {
  content: "\f140";
}
.fa-ellipsis-h:before {
  content: "\f141";
}
.fa-ellipsis-v:before {
  content: "\f142";
}
.fa-rss-square:before {
  content: "\f143";
}
.fa-play-circle:before {
  content: "\f144";
}
.fa-ticket:before {
  content: "\f145";
}
.fa-minus-square:before {
  content: "\f146";
}
.fa-minus-square-o:before {
  content: "\f147";
}
.fa-level-up:before {
  content: "\f148";
}
.fa-level-down:before {
  content: "\f149";
}
.fa-check-square:before {
  content: "\f14a";
}
.fa-pencil-square:before {
  content: "\f14b";
}
.fa-external-link-square:before {
  content: "\f14c";
}
.fa-share-square:before {
  content: "\f14d";
}
.fa-compass:before {
  content: "\f14e";
}
.fa-toggle-down:before,
.fa-caret-square-o-down:before {
  content: "\f150";
}
.fa-toggle-up:before,
.fa-caret-square-o-up:before {
  content: "\f151";
}
.fa-toggle-right:before,
.fa-caret-square-o-right:before {
  content: "\f152";
}
.fa-euro:before,
.fa-eur:before {
  content: "\f153";
}
.fa-gbp:before {
  content: "\f154";
}
.fa-dollar:before,
.fa-usd:before {
  content: "\f155";
}
.fa-rupee:before,
.fa-inr:before {
  content: "\f156";
}
.fa-cny:before,
.fa-rmb:before,
.fa-yen:before,
.fa-jpy:before {
  content: "\f157";
}
.fa-ruble:before,
.fa-rouble:before,
.fa-rub:before {
  content: "\f158";
}
.fa-won:before,
.fa-krw:before {
  content: "\f159";
}
.fa-bitcoin:before,
.fa-btc:before {
  content: "\f15a";
}
.fa-file:before {
  content: "\f15b";
}
.fa-file-text:before {
  content: "\f15c";
}
.fa-sort-alpha-asc:before {
  content: "\f15d";
}
.fa-sort-alpha-desc:before {
  content: "\f15e";
}
.fa-sort-amount-asc:before {
  content: "\f160";
}
.fa-sort-amount-desc:before {
  content: "\f161";
}
.fa-sort-numeric-asc:before {
  content: "\f162";
}
.fa-sort-numeric-desc:before {
  content: "\f163";
}
.fa-thumbs-up:before {
  content: "\f164";
}
.fa-thumbs-down:before {
  content: "\f165";
}
.fa-youtube-square:before {
  content: "\f166";
}
.fa-youtube:before {
  content: "\f167";
}
.fa-xing:before {
  content: "\f168";
}
.fa-xing-square:before {
  content: "\f169";
}
.fa-youtube-play:before {
  content: "\f16a";
}
.fa-dropbox:before {
  content: "\f16b";
}
.fa-stack-overflow:before {
  content: "\f16c";
}
.fa-instagram:before {
  content: "\f16d";
}
.fa-flickr:before {
  content: "\f16e";
}
.fa-adn:before {
  content: "\f170";
}
.fa-bitbucket:before {
  content: "\f171";
}
.fa-bitbucket-square:before {
  content: "\f172";
}
.fa-tumblr:before {
  content: "\f173";
}
.fa-tumblr-square:before {
  content: "\f174";
}
.fa-long-arrow-down:before {
  content: "\f175";
}
.fa-long-arrow-up:before {
  content: "\f176";
}
.fa-long-arrow-left:before {
  content: "\f177";
}
.fa-long-arrow-right:before {
  content: "\f178";
}
.fa-apple:before {
  content: "\f179";
}
.fa-windows:before {
  content: "\f17a";
}
.fa-android:before {
  content: "\f17b";
}
.fa-linux:before {
  content: "\f17c";
}
.fa-dribbble:before {
  content: "\f17d";
}
.fa-skype:before {
  content: "\f17e";
}
.fa-foursquare:before {
  content: "\f180";
}
.fa-trello:before {
  content: "\f181";
}
.fa-female:before {
  content: "\f182";
}
.fa-male:before {
  content: "\f183";
}
.fa-gittip:before,
.fa-gratipay:before {
  content: "\f184";
}
.fa-sun-o:before {
  content: "\f185";
}
.fa-moon-o:before {
  content: "\f186";
}
.fa-archive:before {
  content: "\f187";
}
.fa-bug:before {
  content: "\f188";
}
.fa-vk:before {
  content: "\f189";
}
.fa-weibo:before {
  content: "\f18a";
}
.fa-renren:before {
  content: "\f18b";
}
.fa-pagelines:before {
  content: "\f18c";
}
.fa-stack-exchange:before {
  content: "\f18d";
}
.fa-arrow-circle-o-right:before {
  content: "\f18e";
}
.fa-arrow-circle-o-left:before {
  content: "\f190";
}
.fa-toggle-left:before,
.fa-caret-square-o-left:before {
  content: "\f191";
}
.fa-dot-circle-o:before {
  content: "\f192";
}
.fa-wheelchair:before {
  content: "\f193";
}
.fa-vimeo-square:before {
  content: "\f194";
}
.fa-turkish-lira:before,
.fa-try:before {
  content: "\f195";
}
.fa-plus-square-o:before {
  content: "\f196";
}
.fa-space-shuttle:before {
  content: "\f197";
}
.fa-slack:before {
  content: "\f198";
}
.fa-envelope-square:before {
  content: "\f199";
}
.fa-wordpress:before {
  content: "\f19a";
}
.fa-openid:before {
  content: "\f19b";
}
.fa-institution:before,
.fa-bank:before,
.fa-university:before {
  content: "\f19c";
}
.fa-mortar-board:before,
.fa-graduation-cap:before {
  content: "\f19d";
}
.fa-yahoo:before {
  content: "\f19e";
}
.fa-google:before {
  content: "\f1a0";
}
.fa-reddit:before {
  content: "\f1a1";
}
.fa-reddit-square:before {
  content: "\f1a2";
}
.fa-stumbleupon-circle:before {
  content: "\f1a3";
}
.fa-stumbleupon:before {
  content: "\f1a4";
}
.fa-delicious:before {
  content: "\f1a5";
}
.fa-digg:before {
  content: "\f1a6";
}
.fa-pied-piper-pp:before {
  content: "\f1a7";
}
.fa-pied-piper-alt:before {
  content: "\f1a8";
}
.fa-drupal:before {
  content: "\f1a9";
}
.fa-joomla:before {
  content: "\f1aa";
}
.fa-language:before {
  content: "\f1ab";
}
.fa-fax:before {
  content: "\f1ac";
}
.fa-building:before {
  content: "\f1ad";
}
.fa-child:before {
  content: "\f1ae";
}
.fa-paw:before {
  content: "\f1b0";
}
.fa-spoon:before {
  content: "\f1b1";
}
.fa-cube:before {
  content: "\f1b2";
}
.fa-cubes:before {
  content: "\f1b3";
}
.fa-behance:before {
  content: "\f1b4";
}
.fa-behance-square:before {
  content: "\f1b5";
}
.fa-steam:before {
  content: "\f1b6";
}
.fa-steam-square:before {
  content: "\f1b7";
}
.fa-recycle:before {
  content: "\f1b8";
}
.fa-automobile:before,
.fa-car:before {
  content: "\f1b9";
}
.fa-cab:before,
.fa-taxi:before {
  content: "\f1ba";
}
.fa-tree:before {
  content: "\f1bb";
}
.fa-spotify:before {
  content: "\f1bc";
}
.fa-deviantart:before {
  content: "\f1bd";
}
.fa-soundcloud:before {
  content: "\f1be";
}
.fa-database:before {
  content: "\f1c0";
}
.fa-file-pdf-o:before {
  content: "\f1c1";
}
.fa-file-word-o:before {
  content: "\f1c2";
}
.fa-file-excel-o:before {
  content: "\f1c3";
}
.fa-file-powerpoint-o:before {
  content: "\f1c4";
}
.fa-file-photo-o:before,
.fa-file-picture-o:before,
.fa-file-image-o:before {
  content: "\f1c5";
}
.fa-file-zip-o:before,
.fa-file-archive-o:before {
  content: "\f1c6";
}
.fa-file-sound-o:before,
.fa-file-audio-o:before {
  content: "\f1c7";
}
.fa-file-movie-o:before,
.fa-file-video-o:before {
  content: "\f1c8";
}
.fa-file-code-o:before {
  content: "\f1c9";
}
.fa-vine:before {
  content: "\f1ca";
}
.fa-codepen:before {
  content: "\f1cb";
}
.fa-jsfiddle:before {
  content: "\f1cc";
}
.fa-life-bouy:before,
.fa-life-buoy:before,
.fa-life-saver:before,
.fa-support:before,
.fa-life-ring:before {
  content: "\f1cd";
}
.fa-circle-o-notch:before {
  content: "\f1ce";
}
.fa-ra:before,
.fa-resistance:before,
.fa-rebel:before {
  content: "\f1d0";
}
.fa-ge:before,
.fa-empire:before {
  content: "\f1d1";
}
.fa-git-square:before {
  content: "\f1d2";
}
.fa-git:before {
  content: "\f1d3";
}
.fa-y-combinator-square:before,
.fa-yc-square:before,
.fa-hacker-news:before {
  content: "\f1d4";
}
.fa-tencent-weibo:before {
  content: "\f1d5";
}
.fa-qq:before {
  content: "\f1d6";
}
.fa-wechat:before,
.fa-weixin:before {
  content: "\f1d7";
}
.fa-send:before,
.fa-paper-plane:before {
  content: "\f1d8";
}
.fa-send-o:before,
.fa-paper-plane-o:before {
  content: "\f1d9";
}
.fa-history:before {
  content: "\f1da";
}
.fa-circle-thin:before {
  content: "\f1db";
}
.fa-header:before {
  content: "\f1dc";
}
.fa-paragraph:before {
  content: "\f1dd";
}
.fa-sliders:before {
  content: "\f1de";
}
.fa-share-alt:before {
  content: "\f1e0";
}
.fa-share-alt-square:before {
  content: "\f1e1";
}
.fa-bomb:before {
  content: "\f1e2";
}
.fa-soccer-ball-o:before,
.fa-futbol-o:before {
  content: "\f1e3";
}
.fa-tty:before {
  content: "\f1e4";
}
.fa-binoculars:before {
  content: "\f1e5";
}
.fa-plug:before {
  content: "\f1e6";
}
.fa-slideshare:before {
  content: "\f1e7";
}
.fa-twitch:before {
  content: "\f1e8";
}
.fa-yelp:before {
  content: "\f1e9";
}
.fa-newspaper-o:before {
  content: "\f1ea";
}
.fa-wifi:before {
  content: "\f1eb";
}
.fa-calculator:before {
  content: "\f1ec";
}
.fa-paypal:before {
  content: "\f1ed";
}
.fa-google-wallet:before {
  content: "\f1ee";
}
.fa-cc-visa:before {
  content: "\f1f0";
}
.fa-cc-mastercard:before {
  content: "\f1f1";
}
.fa-cc-discover:before {
  content: "\f1f2";
}
.fa-cc-amex:before {
  content: "\f1f3";
}
.fa-cc-paypal:before {
  content: "\f1f4";
}
.fa-cc-stripe:before {
  content: "\f1f5";
}
.fa-bell-slash:before {
  content: "\f1f6";
}
.fa-bell-slash-o:before {
  content: "\f1f7";
}
.fa-trash:before {
  content: "\f1f8";
}
.fa-copyright:before {
  content: "\f1f9";
}
.fa-at:before {
  content: "\f1fa";
}
.fa-eyedropper:before {
  content: "\f1fb";
}
.fa-paint-brush:before {
  content: "\f1fc";
}
.fa-birthday-cake:before {
  content: "\f1fd";
}
.fa-area-chart:before {
  content: "\f1fe";
}
.fa-pie-chart:before {
  content: "\f200";
}
.fa-line-chart:before {
  content: "\f201";
}
.fa-lastfm:before {
  content: "\f202";
}
.fa-lastfm-square:before {
  content: "\f203";
}
.fa-toggle-off:before {
  content: "\f204";
}
.fa-toggle-on:before {
  content: "\f205";
}
.fa-bicycle:before {
  content: "\f206";
}
.fa-bus:before {
  content: "\f207";
}
.fa-ioxhost:before {
  content: "\f208";
}
.fa-angellist:before {
  content: "\f209";
}
.fa-cc:before {
  content: "\f20a";
}
.fa-shekel:before,
.fa-sheqel:before,
.fa-ils:before {
  content: "\f20b";
}
.fa-meanpath:before {
  content: "\f20c";
}
.fa-buysellads:before {
  content: "\f20d";
}
.fa-connectdevelop:before {
  content: "\f20e";
}
.fa-dashcube:before {
  content: "\f210";
}
.fa-forumbee:before {
  content: "\f211";
}
.fa-leanpub:before {
  content: "\f212";
}
.fa-sellsy:before {
  content: "\f213";
}
.fa-shirtsinbulk:before {
  content: "\f214";
}
.fa-simplybuilt:before {
  content: "\f215";
}
.fa-skyatlas:before {
  content: "\f216";
}
.fa-cart-plus:before {
  content: "\f217";
}
.fa-cart-arrow-down:before {
  content: "\f218";
}
.fa-diamond:before {
  content: "\f219";
}
.fa-ship:before {
  content: "\f21a";
}
.fa-user-secret:before {
  content: "\f21b";
}
.fa-motorcycle:before {
  content: "\f21c";
}
.fa-street-view:before {
  content: "\f21d";
}
.fa-heartbeat:before {
  content: "\f21e";
}
.fa-venus:before {
  content: "\f221";
}
.fa-mars:before {
  content: "\f222";
}
.fa-mercury:before {
  content: "\f223";
}
.fa-intersex:before,
.fa-transgender:before {
  content: "\f224";
}
.fa-transgender-alt:before {
  content: "\f225";
}
.fa-venus-double:before {
  content: "\f226";
}
.fa-mars-double:before {
  content: "\f227";
}
.fa-venus-mars:before {
  content: "\f228";
}
.fa-mars-stroke:before {
  content: "\f229";
}
.fa-mars-stroke-v:before {
  content: "\f22a";
}
.fa-mars-stroke-h:before {
  content: "\f22b";
}
.fa-neuter:before {
  content: "\f22c";
}
.fa-genderless:before {
  content: "\f22d";
}
.fa-facebook-official:before {
  content: "\f230";
}
.fa-pinterest-p:before {
  content: "\f231";
}
.fa-whatsapp:before {
  content: "\f232";
}
.fa-server:before {
  content: "\f233";
}
.fa-user-plus:before {
  content: "\f234";
}
.fa-user-times:before {
  content: "\f235";
}
.fa-hotel:before,
.fa-bed:before {
  content: "\f236";
}
.fa-viacoin:before {
  content: "\f237";
}
.fa-train:before {
  content: "\f238";
}
.fa-subway:before {
  content: "\f239";
}
.fa-medium:before {
  content: "\f23a";
}
.fa-yc:before,
.fa-y-combinator:before {
  content: "\f23b";
}
.fa-optin-monster:before {
  content: "\f23c";
}
.fa-opencart:before {
  content: "\f23d";
}
.fa-expeditedssl:before {
  content: "\f23e";
}
.fa-battery-4:before,
.fa-battery:before,
.fa-battery-full:before {
  content: "\f240";
}
.fa-battery-3:before,
.fa-battery-three-quarters:before {
  content: "\f241";
}
.fa-battery-2:before,
.fa-battery-half:before {
  content: "\f242";
}
.fa-battery-1:before,
.fa-battery-quarter:before {
  content: "\f243";
}
.fa-battery-0:before,
.fa-battery-empty:before {
  content: "\f244";
}
.fa-mouse-pointer:before {
  content: "\f245";
}
.fa-i-cursor:before {
  content: "\f246";
}
.fa-object-group:before {
  content: "\f247";
}
.fa-object-ungroup:before {
  content: "\f248";
}
.fa-sticky-note:before {
  content: "\f249";
}
.fa-sticky-note-o:before {
  content: "\f24a";
}
.fa-cc-jcb:before {
  content: "\f24b";
}
.fa-cc-diners-club:before {
  content: "\f24c";
}
.fa-clone:before {
  content: "\f24d";
}
.fa-balance-scale:before {
  content: "\f24e";
}
.fa-hourglass-o:before {
  content: "\f250";
}
.fa-hourglass-1:before,
.fa-hourglass-start:before {
  content: "\f251";
}
.fa-hourglass-2:before,
.fa-hourglass-half:before {
  content: "\f252";
}
.fa-hourglass-3:before,
.fa-hourglass-end:before {
  content: "\f253";
}
.fa-hourglass:before {
  content: "\f254";
}
.fa-hand-grab-o:before,
.fa-hand-rock-o:before {
  content: "\f255";
}
.fa-hand-stop-o:before,
.fa-hand-paper-o:before {
  content: "\f256";
}
.fa-hand-scissors-o:before {
  content: "\f257";
}
.fa-hand-lizard-o:before {
  content: "\f258";
}
.fa-hand-spock-o:before {
  content: "\f259";
}
.fa-hand-pointer-o:before {
  content: "\f25a";
}
.fa-hand-peace-o:before {
  content: "\f25b";
}
.fa-trademark:before {
  content: "\f25c";
}
.fa-registered:before {
  content: "\f25d";
}
.fa-creative-commons:before {
  content: "\f25e";
}
.fa-gg:before {
  content: "\f260";
}
.fa-gg-circle:before {
  content: "\f261";
}
.fa-tripadvisor:before {
  content: "\f262";
}
.fa-odnoklassniki:before {
  content: "\f263";
}
.fa-odnoklassniki-square:before {
  content: "\f264";
}
.fa-get-pocket:before {
  content: "\f265";
}
.fa-wikipedia-w:before {
  content: "\f266";
}
.fa-safari:before {
  content: "\f267";
}
.fa-chrome:before {
  content: "\f268";
}
.fa-firefox:before {
  content: "\f269";
}
.fa-opera:before {
  content: "\f26a";
}
.fa-internet-explorer:before {
  content: "\f26b";
}
.fa-tv:before,
.fa-television:before {
  content: "\f26c";
}
.fa-contao:before {
  content: "\f26d";
}
.fa-500px:before {
  content: "\f26e";
}
.fa-amazon:before {
  content: "\f270";
}
.fa-calendar-plus-o:before {
  content: "\f271";
}
.fa-calendar-minus-o:before {
  content: "\f272";
}
.fa-calendar-times-o:before {
  content: "\f273";
}
.fa-calendar-check-o:before {
  content: "\f274";
}
.fa-industry:before {
  content: "\f275";
}
.fa-map-pin:before {
  content: "\f276";
}
.fa-map-signs:before {
  content: "\f277";
}
.fa-map-o:before {
  content: "\f278";
}
.fa-map:before {
  content: "\f279";
}
.fa-commenting:before {
  content: "\f27a";
}
.fa-commenting-o:before {
  content: "\f27b";
}
.fa-houzz:before {
  content: "\f27c";
}
.fa-vimeo:before {
  content: "\f27d";
}
.fa-black-tie:before {
  content: "\f27e";
}
.fa-fonticons:before {
  content: "\f280";
}
.fa-reddit-alien:before {
  content: "\f281";
}
.fa-edge:before {
  content: "\f282";
}
.fa-credit-card-alt:before {
  content: "\f283";
}
.fa-codiepie:before {
  content: "\f284";
}
.fa-modx:before {
  content: "\f285";
}
.fa-fort-awesome:before {
  content: "\f286";
}
.fa-usb:before {
  content: "\f287";
}
.fa-product-hunt:before {
  content: "\f288";
}
.fa-mixcloud:before {
  content: "\f289";
}
.fa-scribd:before {
  content: "\f28a";
}
.fa-pause-circle:before {
  content: "\f28b";
}
.fa-pause-circle-o:before {
  content: "\f28c";
}
.fa-stop-circle:before {
  content: "\f28d";
}
.fa-stop-circle-o:before {
  content: "\f28e";
}
.fa-shopping-bag:before {
  content: "\f290";
}
.fa-shopping-basket:before {
  content: "\f291";
}
.fa-hashtag:before {
  content: "\f292";
}
.fa-bluetooth:before {
  content: "\f293";
}
.fa-bluetooth-b:before {
  content: "\f294";
}
.fa-percent:before {
  content: "\f295";
}
.fa-gitlab:before {
  content: "\f296";
}
.fa-wpbeginner:before {
  content: "\f297";
}
.fa-wpforms:before {
  content: "\f298";
}
.fa-envira:before {
  content: "\f299";
}
.fa-universal-access:before {
  content: "\f29a";
}
.fa-wheelchair-alt:before {
  content: "\f29b";
}
.fa-question-circle-o:before {
  content: "\f29c";
}
.fa-blind:before {
  content: "\f29d";
}
.fa-audio-description:before {
  content: "\f29e";
}
.fa-volume-control-phone:before {
  content: "\f2a0";
}
.fa-braille:before {
  content: "\f2a1";
}
.fa-assistive-listening-systems:before {
  content: "\f2a2";
}
.fa-asl-interpreting:before,
.fa-american-sign-language-interpreting:before {
  content: "\f2a3";
}
.fa-deafness:before,
.fa-hard-of-hearing:before,
.fa-deaf:before {
  content: "\f2a4";
}
.fa-glide:before {
  content: "\f2a5";
}
.fa-glide-g:before {
  content: "\f2a6";
}
.fa-signing:before,
.fa-sign-language:before {
  content: "\f2a7";
}
.fa-low-vision:before {
  content: "\f2a8";
}
.fa-viadeo:before {
  content: "\f2a9";
}
.fa-viadeo-square:before {
  content: "\f2aa";
}
.fa-snapchat:before {
  content: "\f2ab";
}
.fa-snapchat-ghost:before {
  content: "\f2ac";
}
.fa-snapchat-square:before {
  content: "\f2ad";
}
.fa-pied-piper:before {
  content: "\f2ae";
}
.fa-first-order:before {
  content: "\f2b0";
}
.fa-yoast:before {
  content: "\f2b1";
}
.fa-themeisle:before {
  content: "\f2b2";
}
.fa-google-plus-circle:before,
.fa-google-plus-official:before {
  content: "\f2b3";
}
.fa-fa:before,
.fa-font-awesome:before {
  content: "\f2b4";
}
.fa-handshake-o:before {
  content: "\f2b5";
}
.fa-envelope-open:before {
  content: "\f2b6";
}
.fa-envelope-open-o:before {
  content: "\f2b7";
}
.fa-linode:before {
  content: "\f2b8";
}
.fa-address-book:before {
  content: "\f2b9";
}
.fa-address-book-o:before {
  content: "\f2ba";
}
.fa-vcard:before,
.fa-address-card:before {
  content: "\f2bb";
}
.fa-vcard-o:before,
.fa-address-card-o:before {
  content: "\f2bc";
}
.fa-user-circle:before {
  content: "\f2bd";
}
.fa-user-circle-o:before {
  content: "\f2be";
}
.fa-user-o:before {
  content: "\f2c0";
}
.fa-id-badge:before {
  content: "\f2c1";
}
.fa-drivers-license:before,
.fa-id-card:before {
  content: "\f2c2";
}
.fa-drivers-license-o:before,
.fa-id-card-o:before {
  content: "\f2c3";
}
.fa-quora:before {
  content: "\f2c4";
}
.fa-free-code-camp:before {
  content: "\f2c5";
}
.fa-telegram:before {
  content: "\f2c6";
}
.fa-thermometer-4:before,
.fa-thermometer:before,
.fa-thermometer-full:before {
  content: "\f2c7";
}
.fa-thermometer-3:before,
.fa-thermometer-three-quarters:before {
  content: "\f2c8";
}
.fa-thermometer-2:before,
.fa-thermometer-half:before {
  content: "\f2c9";
}
.fa-thermometer-1:before,
.fa-thermometer-quarter:before {
  content: "\f2ca";
}
.fa-thermometer-0:before,
.fa-thermometer-empty:before {
  content: "\f2cb";
}
.fa-shower:before {
  content: "\f2cc";
}
.fa-bathtub:before,
.fa-s15:before,
.fa-bath:before {
  content: "\f2cd";
}
.fa-podcast:before {
  content: "\f2ce";
}
.fa-window-maximize:before {
  content: "\f2d0";
}
.fa-window-minimize:before {
  content: "\f2d1";
}
.fa-window-restore:before {
  content: "\f2d2";
}
.fa-times-rectangle:before,
.fa-window-close:before {
  content: "\f2d3";
}
.fa-times-rectangle-o:before,
.fa-window-close-o:before {
  content: "\f2d4";
}
.fa-bandcamp:before {
  content: "\f2d5";
}
.fa-grav:before {
  content: "\f2d6";
}
.fa-etsy:before {
  content: "\f2d7";
}
.fa-imdb:before {
  content: "\f2d8";
}
.fa-ravelry:before {
  content: "\f2d9";
}
.fa-eercast:before {
  content: "\f2da";
}
.fa-microchip:before {
  content: "\f2db";
}
.fa-snowflake-o:before {
  content: "\f2dc";
}
.fa-superpowers:before {
  content: "\f2dd";
}
.fa-wpexplorer:before {
  content: "\f2de";
}
.fa-meetup:before {
  content: "\f2e0";
}
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
/*!
*
* IPython base
*
*/
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
code {
  color: #000;
}
pre {
  font-size: inherit;
  line-height: inherit;
}
label {
  font-weight: normal;
}
/* Make the page background atleast 100% the height of the view port */
/* Make the page itself atleast 70% the height of the view port */
.border-box-sizing {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.corner-all {
  border-radius: 2px;
}
.no-padding {
  padding: 0px;
}
/* Flexible box model classes */
/* Taken from Alex Russell http://infrequently.org/2009/08/css-3-progress/ */
/* This file is a compatability layer.  It allows the usage of flexible box 
model layouts accross multiple browsers, including older browsers.  The newest,
universal implementation of the flexible box model is used when available (see
`Modern browsers` comments below).  Browsers that are known to implement this 
new spec completely include:

    Firefox 28.0+
    Chrome 29.0+
    Internet Explorer 11+ 
    Opera 17.0+

Browsers not listed, including Safari, are supported via the styling under the
`Old browsers` comments below.
*/
.hbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
.hbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.vbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
.vbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.hbox.reverse,
.vbox.reverse,
.reverse {
  /* Old browsers */
  -webkit-box-direction: reverse;
  -moz-box-direction: reverse;
  box-direction: reverse;
  /* Modern browsers */
  flex-direction: row-reverse;
}
.hbox.box-flex0,
.vbox.box-flex0,
.box-flex0 {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
  width: auto;
}
.hbox.box-flex1,
.vbox.box-flex1,
.box-flex1 {
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex,
.vbox.box-flex,
.box-flex {
  /* Old browsers */
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex2,
.vbox.box-flex2,
.box-flex2 {
  /* Old browsers */
  -webkit-box-flex: 2;
  -moz-box-flex: 2;
  box-flex: 2;
  /* Modern browsers */
  flex: 2;
}
.box-group1 {
  /*  Deprecated */
  -webkit-box-flex-group: 1;
  -moz-box-flex-group: 1;
  box-flex-group: 1;
}
.box-group2 {
  /* Deprecated */
  -webkit-box-flex-group: 2;
  -moz-box-flex-group: 2;
  box-flex-group: 2;
}
.hbox.start,
.vbox.start,
.start {
  /* Old browsers */
  -webkit-box-pack: start;
  -moz-box-pack: start;
  box-pack: start;
  /* Modern browsers */
  justify-content: flex-start;
}
.hbox.end,
.vbox.end,
.end {
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
}
.hbox.center,
.vbox.center,
.center {
  /* Old browsers */
  -webkit-box-pack: center;
  -moz-box-pack: center;
  box-pack: center;
  /* Modern browsers */
  justify-content: center;
}
.hbox.baseline,
.vbox.baseline,
.baseline {
  /* Old browsers */
  -webkit-box-pack: baseline;
  -moz-box-pack: baseline;
  box-pack: baseline;
  /* Modern browsers */
  justify-content: baseline;
}
.hbox.stretch,
.vbox.stretch,
.stretch {
  /* Old browsers */
  -webkit-box-pack: stretch;
  -moz-box-pack: stretch;
  box-pack: stretch;
  /* Modern browsers */
  justify-content: stretch;
}
.hbox.align-start,
.vbox.align-start,
.align-start {
  /* Old browsers */
  -webkit-box-align: start;
  -moz-box-align: start;
  box-align: start;
  /* Modern browsers */
  align-items: flex-start;
}
.hbox.align-end,
.vbox.align-end,
.align-end {
  /* Old browsers */
  -webkit-box-align: end;
  -moz-box-align: end;
  box-align: end;
  /* Modern browsers */
  align-items: flex-end;
}
.hbox.align-center,
.vbox.align-center,
.align-center {
  /* Old browsers */
  -webkit-box-align: center;
  -moz-box-align: center;
  box-align: center;
  /* Modern browsers */
  align-items: center;
}
.hbox.align-baseline,
.vbox.align-baseline,
.align-baseline {
  /* Old browsers */
  -webkit-box-align: baseline;
  -moz-box-align: baseline;
  box-align: baseline;
  /* Modern browsers */
  align-items: baseline;
}
.hbox.align-stretch,
.vbox.align-stretch,
.align-stretch {
  /* Old browsers */
  -webkit-box-align: stretch;
  -moz-box-align: stretch;
  box-align: stretch;
  /* Modern browsers */
  align-items: stretch;
}
div.error {
  margin: 2em;
  text-align: center;
}
div.error > h1 {
  font-size: 500%;
  line-height: normal;
}
div.error > p {
  font-size: 200%;
  line-height: normal;
}
div.traceback-wrapper {
  text-align: left;
  max-width: 800px;
  margin: auto;
}
div.traceback-wrapper pre.traceback {
  max-height: 600px;
  overflow: auto;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
body {
  background-color: #fff;
  /* This makes sure that the body covers the entire window and needs to
       be in a different element than the display: box in wrapper below */
  position: absolute;
  left: 0px;
  right: 0px;
  top: 0px;
  bottom: 0px;
  overflow: visible;
}
body > #header {
  /* Initially hidden to prevent FLOUC */
  display: none;
  background-color: #fff;
  /* Display over codemirror */
  position: relative;
  z-index: 100;
}
body > #header #header-container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  padding: 5px;
  padding-bottom: 5px;
  padding-top: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
body > #header .header-bar {
  width: 100%;
  height: 1px;
  background: #e7e7e7;
  margin-bottom: -1px;
}
@media print {
  body > #header {
    display: none !important;
  }
}
#header-spacer {
  width: 100%;
  visibility: hidden;
}
@media print {
  #header-spacer {
    display: none;
  }
}
#ipython_notebook {
  padding-left: 0px;
  padding-top: 1px;
  padding-bottom: 1px;
}
[dir="rtl"] #ipython_notebook {
  margin-right: 10px;
  margin-left: 0;
}
[dir="rtl"] #ipython_notebook.pull-left {
  float: right !important;
  float: right;
}
.flex-spacer {
  flex: 1;
}
#noscript {
  width: auto;
  padding-top: 16px;
  padding-bottom: 16px;
  text-align: center;
  font-size: 22px;
  color: red;
  font-weight: bold;
}
#ipython_notebook img {
  height: 28px;
}
#site {
  width: 100%;
  display: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  overflow: auto;
}
@media print {
  #site {
    height: auto !important;
  }
}
/* Smaller buttons */
.ui-button .ui-button-text {
  padding: 0.2em 0.8em;
  font-size: 77%;
}
input.ui-button {
  padding: 0.3em 0.9em;
}
span#kernel_logo_widget {
  margin: 0 10px;
}
span#login_widget {
  float: right;
}
[dir="rtl"] span#login_widget {
  float: left;
}
span#login_widget > .button,
#logout {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button:focus,
#logout:focus,
span#login_widget > .button.focus,
#logout.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
span#login_widget > .button:hover,
#logout:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active:hover,
#logout:active:hover,
span#login_widget > .button.active:hover,
#logout.active:hover,
.open > .dropdown-togglespan#login_widget > .button:hover,
.open > .dropdown-toggle#logout:hover,
span#login_widget > .button:active:focus,
#logout:active:focus,
span#login_widget > .button.active:focus,
#logout.active:focus,
.open > .dropdown-togglespan#login_widget > .button:focus,
.open > .dropdown-toggle#logout:focus,
span#login_widget > .button:active.focus,
#logout:active.focus,
span#login_widget > .button.active.focus,
#logout.active.focus,
.open > .dropdown-togglespan#login_widget > .button.focus,
.open > .dropdown-toggle#logout.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  background-image: none;
}
span#login_widget > .button.disabled:hover,
#logout.disabled:hover,
span#login_widget > .button[disabled]:hover,
#logout[disabled]:hover,
fieldset[disabled] span#login_widget > .button:hover,
fieldset[disabled] #logout:hover,
span#login_widget > .button.disabled:focus,
#logout.disabled:focus,
span#login_widget > .button[disabled]:focus,
#logout[disabled]:focus,
fieldset[disabled] span#login_widget > .button:focus,
fieldset[disabled] #logout:focus,
span#login_widget > .button.disabled.focus,
#logout.disabled.focus,
span#login_widget > .button[disabled].focus,
#logout[disabled].focus,
fieldset[disabled] span#login_widget > .button.focus,
fieldset[disabled] #logout.focus {
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button .badge,
#logout .badge {
  color: #fff;
  background-color: #333;
}
.nav-header {
  text-transform: none;
}
#header > span {
  margin-top: 10px;
}
.modal_stretch .modal-dialog {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  min-height: 80vh;
}
.modal_stretch .modal-dialog .modal-body {
  max-height: calc(100vh - 200px);
  overflow: auto;
  flex: 1;
}
.modal-header {
  cursor: move;
}
@media (min-width: 768px) {
  .modal .modal-dialog {
    width: 700px;
  }
}
@media (min-width: 768px) {
  select.form-control {
    margin-left: 12px;
    margin-right: 12px;
  }
}
/*!
*
* IPython auth
*
*/
.center-nav {
  display: inline-block;
  margin-bottom: -4px;
}
[dir="rtl"] .center-nav form.pull-left {
  float: right !important;
  float: right;
}
[dir="rtl"] .center-nav .navbar-text {
  float: right;
}
[dir="rtl"] .navbar-inner {
  text-align: right;
}
[dir="rtl"] div.text-left {
  text-align: right;
}
/*!
*
* IPython tree view
*
*/
/* We need an invisible input field on top of the sentense*/
/* "Drag file onto the list ..." */
.alternate_upload {
  background-color: none;
  display: inline;
}
.alternate_upload.form {
  padding: 0;
  margin: 0;
}
.alternate_upload input.fileinput {
  position: absolute;
  display: block;
  width: 100%;
  height: 100%;
  overflow: hidden;
  cursor: pointer;
  opacity: 0;
  z-index: 2;
}
.alternate_upload .btn-xs > input.fileinput {
  margin: -1px -5px;
}
.alternate_upload .btn-upload {
  position: relative;
  height: 22px;
}
::-webkit-file-upload-button {
  cursor: pointer;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
ul#tabs {
  margin-bottom: 4px;
}
ul#tabs a {
  padding-top: 6px;
  padding-bottom: 4px;
}
[dir="rtl"] ul#tabs.nav-tabs > li {
  float: right;
}
[dir="rtl"] ul#tabs.nav.nav-tabs {
  padding-right: 0;
}
ul.breadcrumb a:focus,
ul.breadcrumb a:hover {
  text-decoration: none;
}
ul.breadcrumb i.icon-home {
  font-size: 16px;
  margin-right: 4px;
}
ul.breadcrumb span {
  color: #5e5e5e;
}
.list_toolbar {
  padding: 4px 0 4px 0;
  vertical-align: middle;
}
.list_toolbar .tree-buttons {
  padding-top: 1px;
}
[dir="rtl"] .list_toolbar .tree-buttons .pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .list_toolbar .col-sm-4,
[dir="rtl"] .list_toolbar .col-sm-8 {
  float: right;
}
.dynamic-buttons {
  padding-top: 3px;
  display: inline-block;
}
.list_toolbar [class*="span"] {
  min-height: 24px;
}
.list_header {
  font-weight: bold;
  background-color: #EEE;
}
.list_placeholder {
  font-weight: bold;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
}
.list_container {
  margin-top: 4px;
  margin-bottom: 20px;
  border: 1px solid #ddd;
  border-radius: 2px;
}
.list_container > div {
  border-bottom: 1px solid #ddd;
}
.list_container > div:hover .list-item {
  background-color: red;
}
.list_container > div:last-child {
  border: none;
}
.list_item:hover .list_item {
  background-color: #ddd;
}
.list_item a {
  text-decoration: none;
}
.list_item:hover {
  background-color: #fafafa;
}
.list_header > div,
.list_item > div {
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
.list_header > div input,
.list_item > div input {
  margin-right: 7px;
  margin-left: 14px;
  vertical-align: text-bottom;
  line-height: 22px;
  position: relative;
  top: -1px;
}
.list_header > div .item_link,
.list_item > div .item_link {
  margin-left: -1px;
  vertical-align: baseline;
  line-height: 22px;
}
[dir="rtl"] .list_item > div input {
  margin-right: 0;
}
.new-file input[type=checkbox] {
  visibility: hidden;
}
.item_name {
  line-height: 22px;
  height: 24px;
}
.item_icon {
  font-size: 14px;
  color: #5e5e5e;
  margin-right: 7px;
  margin-left: 7px;
  line-height: 22px;
  vertical-align: baseline;
}
.item_modified {
  margin-right: 7px;
  margin-left: 7px;
}
[dir="rtl"] .item_modified.pull-right {
  float: left !important;
  float: left;
}
.item_buttons {
  line-height: 1em;
  margin-left: -5px;
}
.item_buttons .btn,
.item_buttons .btn-group,
.item_buttons .input-group {
  float: left;
}
.item_buttons > .btn,
.item_buttons > .btn-group,
.item_buttons > .input-group {
  margin-left: 5px;
}
.item_buttons .btn {
  min-width: 13ex;
}
.item_buttons .running-indicator {
  padding-top: 4px;
  color: #5cb85c;
}
.item_buttons .kernel-name {
  padding-top: 4px;
  color: #5bc0de;
  margin-right: 7px;
  float: left;
}
[dir="rtl"] .item_buttons.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .item_buttons .kernel-name {
  margin-left: 7px;
  float: right;
}
.toolbar_info {
  height: 24px;
  line-height: 24px;
}
.list_item input:not([type=checkbox]) {
  padding-top: 3px;
  padding-bottom: 3px;
  height: 22px;
  line-height: 14px;
  margin: 0px;
}
.highlight_text {
  color: blue;
}
#project_name {
  display: inline-block;
  padding-left: 7px;
  margin-left: -2px;
}
#project_name > .breadcrumb {
  padding: 0px;
  margin-bottom: 0px;
  background-color: transparent;
  font-weight: bold;
}
.sort_button {
  display: inline-block;
  padding-left: 7px;
}
[dir="rtl"] .sort_button.pull-right {
  float: left !important;
  float: left;
}
#tree-selector {
  padding-right: 0px;
}
#button-select-all {
  min-width: 50px;
}
[dir="rtl"] #button-select-all.btn {
  float: right ;
}
#select-all {
  margin-left: 7px;
  margin-right: 2px;
  margin-top: 2px;
  height: 16px;
}
[dir="rtl"] #select-all.pull-left {
  float: right !important;
  float: right;
}
.menu_icon {
  margin-right: 2px;
}
.tab-content .row {
  margin-left: 0px;
  margin-right: 0px;
}
.folder_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f114";
}
.folder_icon:before.fa-pull-left {
  margin-right: .3em;
}
.folder_icon:before.fa-pull-right {
  margin-left: .3em;
}
.folder_icon:before.pull-left {
  margin-right: .3em;
}
.folder_icon:before.pull-right {
  margin-left: .3em;
}
.notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
}
.notebook_icon:before.fa-pull-left {
  margin-right: .3em;
}
.notebook_icon:before.fa-pull-right {
  margin-left: .3em;
}
.notebook_icon:before.pull-left {
  margin-right: .3em;
}
.notebook_icon:before.pull-right {
  margin-left: .3em;
}
.running_notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
  color: #5cb85c;
}
.running_notebook_icon:before.fa-pull-left {
  margin-right: .3em;
}
.running_notebook_icon:before.fa-pull-right {
  margin-left: .3em;
}
.running_notebook_icon:before.pull-left {
  margin-right: .3em;
}
.running_notebook_icon:before.pull-right {
  margin-left: .3em;
}
.file_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f016";
  position: relative;
  top: -2px;
}
.file_icon:before.fa-pull-left {
  margin-right: .3em;
}
.file_icon:before.fa-pull-right {
  margin-left: .3em;
}
.file_icon:before.pull-left {
  margin-right: .3em;
}
.file_icon:before.pull-right {
  margin-left: .3em;
}
#notebook_toolbar .pull-right {
  padding-top: 0px;
  margin-right: -1px;
}
ul#new-menu {
  left: auto;
  right: 0;
}
#new-menu .dropdown-header {
  font-size: 10px;
  border-bottom: 1px solid #e5e5e5;
  padding: 0 0 3px;
  margin: -3px 20px 0;
}
.kernel-menu-icon {
  padding-right: 12px;
  width: 24px;
  content: "\f096";
}
.kernel-menu-icon:before {
  content: "\f096";
}
.kernel-menu-icon-current:before {
  content: "\f00c";
}
#tab_content {
  padding-top: 20px;
}
#running .panel-group .panel {
  margin-top: 3px;
  margin-bottom: 1em;
}
#running .panel-group .panel .panel-heading {
  background-color: #EEE;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
#running .panel-group .panel .panel-heading a:focus,
#running .panel-group .panel .panel-heading a:hover {
  text-decoration: none;
}
#running .panel-group .panel .panel-body {
  padding: 0px;
}
#running .panel-group .panel .panel-body .list_container {
  margin-top: 0px;
  margin-bottom: 0px;
  border: 0px;
  border-radius: 0px;
}
#running .panel-group .panel .panel-body .list_container .list_item {
  border-bottom: 1px solid #ddd;
}
#running .panel-group .panel .panel-body .list_container .list_item:last-child {
  border-bottom: 0px;
}
.delete-button {
  display: none;
}
.duplicate-button {
  display: none;
}
.rename-button {
  display: none;
}
.move-button {
  display: none;
}
.download-button {
  display: none;
}
.shutdown-button {
  display: none;
}
.dynamic-instructions {
  display: inline-block;
  padding-top: 4px;
}
/*!
*
* IPython text editor webapp
*
*/
.selected-keymap i.fa {
  padding: 0px 5px;
}
.selected-keymap i.fa:before {
  content: "\f00c";
}
#mode-menu {
  overflow: auto;
  max-height: 20em;
}
.edit_app #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.edit_app #menubar .navbar {
  /* Use a negative 1 bottom margin, so the border overlaps the border of the
    header */
  margin-bottom: -1px;
}
.dirty-indicator {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator.pull-left {
  margin-right: .3em;
}
.dirty-indicator.pull-right {
  margin-left: .3em;
}
.dirty-indicator-dirty {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-dirty.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-dirty.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-dirty.pull-left {
  margin-right: .3em;
}
.dirty-indicator-dirty.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-clean.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f00c";
}
.dirty-indicator-clean:before.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean:before.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean:before.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean:before.pull-right {
  margin-left: .3em;
}
#filename {
  font-size: 16pt;
  display: table;
  padding: 0px 5px;
}
#current-mode {
  padding-left: 5px;
  padding-right: 5px;
}
#texteditor-backdrop {
  padding-top: 20px;
  padding-bottom: 20px;
}
@media not print {
  #texteditor-backdrop {
    background-color: #EEE;
  }
}
@media print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container {
    padding: 0px;
    background-color: #fff;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
.CodeMirror-dialog {
  background-color: #fff;
}
/*!
*
* IPython notebook
*
*/
/* CSS font colors for translated ANSI escape sequences */
/* The color values are a mix of
   http://www.xcolors.net/dl/baskerville-ivorylight and
   http://www.xcolors.net/dl/euphrasia */
.ansi-black-fg {
  color: #3E424D;
}
.ansi-black-bg {
  background-color: #3E424D;
}
.ansi-black-intense-fg {
  color: #282C36;
}
.ansi-black-intense-bg {
  background-color: #282C36;
}
.ansi-red-fg {
  color: #E75C58;
}
.ansi-red-bg {
  background-color: #E75C58;
}
.ansi-red-intense-fg {
  color: #B22B31;
}
.ansi-red-intense-bg {
  background-color: #B22B31;
}
.ansi-green-fg {
  color: #00A250;
}
.ansi-green-bg {
  background-color: #00A250;
}
.ansi-green-intense-fg {
  color: #007427;
}
.ansi-green-intense-bg {
  background-color: #007427;
}
.ansi-yellow-fg {
  color: #DDB62B;
}
.ansi-yellow-bg {
  background-color: #DDB62B;
}
.ansi-yellow-intense-fg {
  color: #B27D12;
}
.ansi-yellow-intense-bg {
  background-color: #B27D12;
}
.ansi-blue-fg {
  color: #208FFB;
}
.ansi-blue-bg {
  background-color: #208FFB;
}
.ansi-blue-intense-fg {
  color: #0065CA;
}
.ansi-blue-intense-bg {
  background-color: #0065CA;
}
.ansi-magenta-fg {
  color: #D160C4;
}
.ansi-magenta-bg {
  background-color: #D160C4;
}
.ansi-magenta-intense-fg {
  color: #A03196;
}
.ansi-magenta-intense-bg {
  background-color: #A03196;
}
.ansi-cyan-fg {
  color: #60C6C8;
}
.ansi-cyan-bg {
  background-color: #60C6C8;
}
.ansi-cyan-intense-fg {
  color: #258F8F;
}
.ansi-cyan-intense-bg {
  background-color: #258F8F;
}
.ansi-white-fg {
  color: #C5C1B4;
}
.ansi-white-bg {
  background-color: #C5C1B4;
}
.ansi-white-intense-fg {
  color: #A1A6B2;
}
.ansi-white-intense-bg {
  background-color: #A1A6B2;
}
.ansi-default-inverse-fg {
  color: #FFFFFF;
}
.ansi-default-inverse-bg {
  background-color: #000000;
}
.ansi-bold {
  font-weight: bold;
}
.ansi-underline {
  text-decoration: underline;
}
/* The following styles are deprecated an will be removed in a future version */
.ansibold {
  font-weight: bold;
}
.ansi-inverse {
  outline: 0.5px dotted;
}
/* use dark versions for foreground, to improve visibility */
.ansiblack {
  color: black;
}
.ansired {
  color: darkred;
}
.ansigreen {
  color: darkgreen;
}
.ansiyellow {
  color: #c4a000;
}
.ansiblue {
  color: darkblue;
}
.ansipurple {
  color: darkviolet;
}
.ansicyan {
  color: steelblue;
}
.ansigray {
  color: gray;
}
/* and light for background, for the same reason */
.ansibgblack {
  background-color: black;
}
.ansibgred {
  background-color: red;
}
.ansibggreen {
  background-color: green;
}
.ansibgyellow {
  background-color: yellow;
}
.ansibgblue {
  background-color: blue;
}
.ansibgpurple {
  background-color: magenta;
}
.ansibgcyan {
  background-color: cyan;
}
.ansibggray {
  background-color: gray;
}
div.cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  border-radius: 2px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  border-width: 1px;
  border-style: solid;
  border-color: transparent;
  width: 100%;
  padding: 5px;
  /* This acts as a spacer between cells, that is outside the border */
  margin: 0px;
  outline: none;
  position: relative;
  overflow: visible;
}
div.cell:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: transparent;
}
div.cell.jupyter-soft-selected {
  border-left-color: #E3F2FD;
  border-left-width: 1px;
  padding-left: 5px;
  border-right-color: #E3F2FD;
  border-right-width: 1px;
  background: #E3F2FD;
}
@media print {
  div.cell.jupyter-soft-selected {
    border-color: transparent;
  }
}
div.cell.selected,
div.cell.selected.jupyter-soft-selected {
  border-color: #ababab;
}
div.cell.selected:before,
div.cell.selected.jupyter-soft-selected:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: #42A5F5;
}
@media print {
  div.cell.selected,
  div.cell.selected.jupyter-soft-selected {
    border-color: transparent;
  }
}
.edit_mode div.cell.selected {
  border-color: #66BB6A;
}
.edit_mode div.cell.selected:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: #66BB6A;
}
@media print {
  .edit_mode div.cell.selected {
    border-color: transparent;
  }
}
.prompt {
  /* This needs to be wide enough for 3 digit prompt numbers: In[100]: */
  min-width: 14ex;
  /* This padding is tuned to match the padding on the CodeMirror editor. */
  padding: 0.4em;
  margin: 0px;
  font-family: monospace;
  text-align: right;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
  /* Don't highlight prompt number selection */
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  /* Use default cursor */
  cursor: default;
}
@media (max-width: 540px) {
  .prompt {
    text-align: left;
  }
}
div.inner_cell {
  min-width: 0;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_area {
  border: 1px solid #cfcfcf;
  border-radius: 2px;
  background: #f7f7f7;
  line-height: 1.21429em;
}
/* This is needed so that empty prompt areas can collapse to zero height when there
   is no content in the output_subarea and the prompt. The main purpose of this is
   to make sure that empty JavaScript output_subareas have no height. */
div.prompt:empty {
  padding-top: 0;
  padding-bottom: 0;
}
div.unrecognized_cell {
  padding: 5px 5px 5px 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.unrecognized_cell .inner_cell {
  border-radius: 2px;
  padding: 5px;
  font-weight: bold;
  color: red;
  border: 1px solid #cfcfcf;
  background: #eaeaea;
}
div.unrecognized_cell .inner_cell a {
  color: inherit;
  text-decoration: none;
}
div.unrecognized_cell .inner_cell a:hover {
  color: inherit;
  text-decoration: none;
}
@media (max-width: 540px) {
  div.unrecognized_cell > div.prompt {
    display: none;
  }
}
div.code_cell {
  /* avoid page breaking on code cells when printing */
}
@media print {
  div.code_cell {
    page-break-inside: avoid;
  }
}
/* any special styling for code cells that are currently running goes here */
div.input {
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.input {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_prompt {
  color: #303F9F;
  border-top: 1px solid transparent;
}
div.input_area > div.highlight {
  margin: 0.4em;
  border: none;
  padding: 0px;
  background-color: transparent;
}
div.input_area > div.highlight > pre {
  margin: 0px;
  border: none;
  padding: 0px;
  background-color: transparent;
}
/* The following gets added to the <head> if it is detected that the user has a
 * monospace font with inconsistent normal/bold/italic height.  See
 * notebookmain.js.  Such fonts will have keywords vertically offset with
 * respect to the rest of the text.  The user should select a better font.
 * See: https://github.com/ipython/ipython/issues/1503
 *
 * .CodeMirror span {
 *      vertical-align: bottom;
 * }
 */
.CodeMirror {
  line-height: 1.21429em;
  /* Changed from 1em to our global default */
  font-size: 14px;
  height: auto;
  /* Changed to auto to autogrow */
  background: none;
  /* Changed from white to allow our bg to show through */
}
.CodeMirror-scroll {
  /*  The CodeMirror docs are a bit fuzzy on if overflow-y should be hidden or visible.*/
  /*  We have found that if it is visible, vertical scrollbars appear with font size changes.*/
  overflow-y: hidden;
  overflow-x: auto;
}
.CodeMirror-lines {
  /* In CM2, this used to be 0.4em, but in CM3 it went to 4px. We need the em value because */
  /* we have set a different line-height and want this to scale with that. */
  /* Note that this should set vertical padding only, since CodeMirror assumes
       that horizontal padding will be set on CodeMirror pre */
  padding: 0.4em 0;
}
.CodeMirror-linenumber {
  padding: 0 8px 0 4px;
}
.CodeMirror-gutters {
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.CodeMirror pre {
  /* In CM3 this went to 4px from 0 in CM2. This sets horizontal padding only,
    use .CodeMirror-lines for vertical */
  padding: 0 0.4em;
  border: 0;
  border-radius: 0;
}
.CodeMirror-cursor {
  border-left: 1.4px solid black;
}
@media screen and (min-width: 2138px) and (max-width: 4319px) {
  .CodeMirror-cursor {
    border-left: 2px solid black;
  }
}
@media screen and (min-width: 4320px) {
  .CodeMirror-cursor {
    border-left: 4px solid black;
  }
}
/*

Original style from softwaremaniacs.org (c) Ivan Sagalaev <Maniac@SoftwareManiacs.Org>
Adapted from GitHub theme

*/
.highlight-base {
  color: #000;
}
.highlight-variable {
  color: #000;
}
.highlight-variable-2 {
  color: #1a1a1a;
}
.highlight-variable-3 {
  color: #333333;
}
.highlight-string {
  color: #BA2121;
}
.highlight-comment {
  color: #408080;
  font-style: italic;
}
.highlight-number {
  color: #080;
}
.highlight-atom {
  color: #88F;
}
.highlight-keyword {
  color: #008000;
  font-weight: bold;
}
.highlight-builtin {
  color: #008000;
}
.highlight-error {
  color: #f00;
}
.highlight-operator {
  color: #AA22FF;
  font-weight: bold;
}
.highlight-meta {
  color: #AA22FF;
}
/* previously not defined, copying from default codemirror */
.highlight-def {
  color: #00f;
}
.highlight-string-2 {
  color: #f50;
}
.highlight-qualifier {
  color: #555;
}
.highlight-bracket {
  color: #997;
}
.highlight-tag {
  color: #170;
}
.highlight-attribute {
  color: #00c;
}
.highlight-header {
  color: blue;
}
.highlight-quote {
  color: #090;
}
.highlight-link {
  color: #00c;
}
/* apply the same style to codemirror */
.cm-s-ipython span.cm-keyword {
  color: #008000;
  font-weight: bold;
}
.cm-s-ipython span.cm-atom {
  color: #88F;
}
.cm-s-ipython span.cm-number {
  color: #080;
}
.cm-s-ipython span.cm-def {
  color: #00f;
}
.cm-s-ipython span.cm-variable {
  color: #000;
}
.cm-s-ipython span.cm-operator {
  color: #AA22FF;
  font-weight: bold;
}
.cm-s-ipython span.cm-variable-2 {
  color: #1a1a1a;
}
.cm-s-ipython span.cm-variable-3 {
  color: #333333;
}
.cm-s-ipython span.cm-comment {
  color: #408080;
  font-style: italic;
}
.cm-s-ipython span.cm-string {
  color: #BA2121;
}
.cm-s-ipython span.cm-string-2 {
  color: #f50;
}
.cm-s-ipython span.cm-meta {
  color: #AA22FF;
}
.cm-s-ipython span.cm-qualifier {
  color: #555;
}
.cm-s-ipython span.cm-builtin {
  color: #008000;
}
.cm-s-ipython span.cm-bracket {
  color: #997;
}
.cm-s-ipython span.cm-tag {
  color: #170;
}
.cm-s-ipython span.cm-attribute {
  color: #00c;
}
.cm-s-ipython span.cm-header {
  color: blue;
}
.cm-s-ipython span.cm-quote {
  color: #090;
}
.cm-s-ipython span.cm-link {
  color: #00c;
}
.cm-s-ipython span.cm-error {
  color: #f00;
}
.cm-s-ipython span.cm-tab {
  background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAMCAYAAAAkuj5RAAAAAXNSR0IArs4c6QAAAGFJREFUSMft1LsRQFAQheHPowAKoACx3IgEKtaEHujDjORSgWTH/ZOdnZOcM/sgk/kFFWY0qV8foQwS4MKBCS3qR6ixBJvElOobYAtivseIE120FaowJPN75GMu8j/LfMwNjh4HUpwg4LUAAAAASUVORK5CYII=);
  background-position: right;
  background-repeat: no-repeat;
}
div.output_wrapper {
  /* this position must be relative to enable descendents to be absolute within it */
  position: relative;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  z-index: 1;
}
/* class for the output area when it should be height-limited */
div.output_scroll {
  /* ideally, this would be max-height, but FF barfs all over that */
  height: 24em;
  /* FF needs this *and the wrapper* to specify full width, or it will shrinkwrap */
  width: 100%;
  overflow: auto;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  display: block;
}
/* output div while it is collapsed */
div.output_collapsed {
  margin: 0px;
  padding: 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
div.out_prompt_overlay {
  height: 100%;
  padding: 0px 0.4em;
  position: absolute;
  border-radius: 2px;
}
div.out_prompt_overlay:hover {
  /* use inner shadow to get border that is computed the same on WebKit/FF */
  -webkit-box-shadow: inset 0 0 1px #000;
  box-shadow: inset 0 0 1px #000;
  background: rgba(240, 240, 240, 0.5);
}
div.output_prompt {
  color: #D84315;
}
/* This class is the outer container of all output sections. */
div.output_area {
  padding: 0px;
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.output_area .MathJax_Display {
  text-align: left !important;
}
div.output_area .rendered_html table {
  margin-left: 0;
  margin-right: 0;
}
div.output_area .rendered_html img {
  margin-left: 0;
  margin-right: 0;
}
div.output_area img,
div.output_area svg {
  max-width: 100%;
  height: auto;
}
div.output_area img.unconfined,
div.output_area svg.unconfined {
  max-width: none;
}
div.output_area .mglyph > img {
  max-width: none;
}
/* This is needed to protect the pre formating from global settings such
   as that of bootstrap */
.output {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.output_area {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
div.output_area pre {
  margin: 0;
  padding: 1px 0 1px 0;
  border: 0;
  vertical-align: baseline;
  color: black;
  background-color: transparent;
  border-radius: 0;
}
/* This class is for the output subarea inside the output_area and after
   the prompt div. */
div.output_subarea {
  overflow-x: auto;
  padding: 0.4em;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
  max-width: calc(100% - 14ex);
}
div.output_scroll div.output_subarea {
  overflow-x: visible;
}
/* The rest of the output_* classes are for special styling of the different
   output types */
/* all text output has this class: */
div.output_text {
  text-align: left;
  color: #000;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
}
/* stdout/stderr are 'text' as well as 'stream', but execute_result/error are *not* streams */
div.output_stderr {
  background: #fdd;
  /* very light red background for stderr */
}
div.output_latex {
  text-align: left;
}
/* Empty output_javascript divs should have no height */
div.output_javascript:empty {
  padding: 0;
}
.js-error {
  color: darkred;
}
/* raw_input styles */
div.raw_input_container {
  line-height: 1.21429em;
  padding-top: 5px;
}
pre.raw_input_prompt {
  /* nothing needed here. */
}
input.raw_input {
  font-family: monospace;
  font-size: inherit;
  color: inherit;
  width: auto;
  /* make sure input baseline aligns with prompt */
  vertical-align: baseline;
  /* padding + margin = 0.5em between prompt and cursor */
  padding: 0em 0.25em;
  margin: 0em 0.25em;
}
input.raw_input:focus {
  box-shadow: none;
}
p.p-space {
  margin-bottom: 10px;
}
div.output_unrecognized {
  padding: 5px;
  font-weight: bold;
  color: red;
}
div.output_unrecognized a {
  color: inherit;
  text-decoration: none;
}
div.output_unrecognized a:hover {
  color: inherit;
  text-decoration: none;
}
.rendered_html {
  color: #000;
  /* any extras will just be numbers: */
}
.rendered_html em {
  font-style: italic;
}
.rendered_html strong {
  font-weight: bold;
}
.rendered_html u {
  text-decoration: underline;
}
.rendered_html :link {
  text-decoration: underline;
}
.rendered_html :visited {
  text-decoration: underline;
}
.rendered_html h1 {
  font-size: 185.7%;
  margin: 1.08em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h2 {
  font-size: 157.1%;
  margin: 1.27em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h3 {
  font-size: 128.6%;
  margin: 1.55em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h4 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h5 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h6 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h1:first-child {
  margin-top: 0.538em;
}
.rendered_html h2:first-child {
  margin-top: 0.636em;
}
.rendered_html h3:first-child {
  margin-top: 0.777em;
}
.rendered_html h4:first-child {
  margin-top: 1em;
}
.rendered_html h5:first-child {
  margin-top: 1em;
}
.rendered_html h6:first-child {
  margin-top: 1em;
}
.rendered_html ul:not(.list-inline),
.rendered_html ol:not(.list-inline) {
  padding-left: 2em;
}
.rendered_html ul {
  list-style: disc;
}
.rendered_html ul ul {
  list-style: square;
  margin-top: 0;
}
.rendered_html ul ul ul {
  list-style: circle;
}
.rendered_html ol {
  list-style: decimal;
}
.rendered_html ol ol {
  list-style: upper-alpha;
  margin-top: 0;
}
.rendered_html ol ol ol {
  list-style: lower-alpha;
}
.rendered_html ol ol ol ol {
  list-style: lower-roman;
}
.rendered_html ol ol ol ol ol {
  list-style: decimal;
}
.rendered_html * + ul {
  margin-top: 1em;
}
.rendered_html * + ol {
  margin-top: 1em;
}
.rendered_html hr {
  color: black;
  background-color: black;
}
.rendered_html pre {
  margin: 1em 2em;
  padding: 0px;
  background-color: #fff;
}
.rendered_html code {
  background-color: #eff0f1;
}
.rendered_html p code {
  padding: 1px 5px;
}
.rendered_html pre code {
  background-color: #fff;
}
.rendered_html pre,
.rendered_html code {
  border: 0;
  color: #000;
  font-size: 100%;
}
.rendered_html blockquote {
  margin: 1em 2em;
}
.rendered_html table {
  margin-left: auto;
  margin-right: auto;
  border: none;
  border-collapse: collapse;
  border-spacing: 0;
  color: black;
  font-size: 12px;
  table-layout: fixed;
}
.rendered_html thead {
  border-bottom: 1px solid black;
  vertical-align: bottom;
}
.rendered_html tr,
.rendered_html th,
.rendered_html td {
  text-align: right;
  vertical-align: middle;
  padding: 0.5em 0.5em;
  line-height: normal;
  white-space: normal;
  max-width: none;
  border: none;
}
.rendered_html th {
  font-weight: bold;
}
.rendered_html tbody tr:nth-child(odd) {
  background: #f5f5f5;
}
.rendered_html tbody tr:hover {
  background: rgba(66, 165, 245, 0.2);
}
.rendered_html * + table {
  margin-top: 1em;
}
.rendered_html p {
  text-align: left;
}
.rendered_html * + p {
  margin-top: 1em;
}
.rendered_html img {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.rendered_html * + img {
  margin-top: 1em;
}
.rendered_html img,
.rendered_html svg {
  max-width: 100%;
  height: auto;
}
.rendered_html img.unconfined,
.rendered_html svg.unconfined {
  max-width: none;
}
.rendered_html .alert {
  margin-bottom: initial;
}
.rendered_html * + .alert {
  margin-top: 1em;
}
[dir="rtl"] .rendered_html p {
  text-align: right;
}
div.text_cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.text_cell > div.prompt {
    display: none;
  }
}
div.text_cell_render {
  /*font-family: "Helvetica Neue", Arial, Helvetica, Geneva, sans-serif;*/
  outline: none;
  resize: none;
  width: inherit;
  border-style: none;
  padding: 0.5em 0.5em 0.5em 0.4em;
  color: #000;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
a.anchor-link:link {
  text-decoration: none;
  padding: 0px 20px;
  visibility: hidden;
}
h1:hover .anchor-link,
h2:hover .anchor-link,
h3:hover .anchor-link,
h4:hover .anchor-link,
h5:hover .anchor-link,
h6:hover .anchor-link {
  visibility: visible;
}
.text_cell.rendered .input_area {
  display: none;
}
.text_cell.rendered .rendered_html {
  overflow-x: auto;
  overflow-y: hidden;
}
.text_cell.rendered .rendered_html tr,
.text_cell.rendered .rendered_html th,
.text_cell.rendered .rendered_html td {
  max-width: none;
}
.text_cell.unrendered .text_cell_render {
  display: none;
}
.text_cell .dropzone .input_area {
  border: 2px dashed #bababa;
  margin: -1px;
}
.cm-header-1,
.cm-header-2,
.cm-header-3,
.cm-header-4,
.cm-header-5,
.cm-header-6 {
  font-weight: bold;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
}
.cm-header-1 {
  font-size: 185.7%;
}
.cm-header-2 {
  font-size: 157.1%;
}
.cm-header-3 {
  font-size: 128.6%;
}
.cm-header-4 {
  font-size: 110%;
}
.cm-header-5 {
  font-size: 100%;
  font-style: italic;
}
.cm-header-6 {
  font-size: 100%;
  font-style: italic;
}
/*!
*
* IPython notebook webapp
*
*/
@media (max-width: 767px) {
  .notebook_app {
    padding-left: 0px;
    padding-right: 0px;
  }
}
#ipython-main-app {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook_panel {
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook {
  font-size: 14px;
  line-height: 20px;
  overflow-y: hidden;
  overflow-x: auto;
  width: 100%;
  /* This spaces the page away from the edge of the notebook area */
  padding-top: 20px;
  margin: 0px;
  outline: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  min-height: 100%;
}
@media not print {
  #notebook-container {
    padding: 15px;
    background-color: #fff;
    min-height: 0;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
@media print {
  #notebook-container {
    width: 100%;
  }
}
div.ui-widget-content {
  border: 1px solid #ababab;
  outline: none;
}
pre.dialog {
  background-color: #f7f7f7;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0.4em;
  padding-left: 2em;
}
p.dialog {
  padding: 0.2em;
}
/* Word-wrap output correctly.  This is the CSS3 spelling, though Firefox seems
   to not honor it correctly.  Webkit browsers (Chrome, rekonq, Safari) do.
 */
pre,
code,
kbd,
samp {
  white-space: pre-wrap;
}
#fonttest {
  font-family: monospace;
}
p {
  margin-bottom: 0;
}
.end_space {
  min-height: 100px;
  transition: height .2s ease;
}
.notebook_app > #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
@media not print {
  .notebook_app {
    background-color: #EEE;
  }
}
kbd {
  border-style: solid;
  border-width: 1px;
  box-shadow: none;
  margin: 2px;
  padding-left: 2px;
  padding-right: 2px;
  padding-top: 1px;
  padding-bottom: 1px;
}
.jupyter-keybindings {
  padding: 1px;
  line-height: 24px;
  border-bottom: 1px solid gray;
}
.jupyter-keybindings input {
  margin: 0;
  padding: 0;
  border: none;
}
.jupyter-keybindings i {
  padding: 6px;
}
.well code {
  background-color: #ffffff;
  border-color: #ababab;
  border-width: 1px;
  border-style: solid;
  padding: 2px;
  padding-top: 1px;
  padding-bottom: 1px;
}
/* CSS for the cell toolbar */
.celltoolbar {
  border: thin solid #CFCFCF;
  border-bottom: none;
  background: #EEE;
  border-radius: 2px 2px 0px 0px;
  width: 100%;
  height: 29px;
  padding-right: 4px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
  display: -webkit-flex;
}
@media print {
  .celltoolbar {
    display: none;
  }
}
.ctb_hideshow {
  display: none;
  vertical-align: bottom;
}
/* ctb_show is added to the ctb_hideshow div to show the cell toolbar.
   Cell toolbars are only shown when the ctb_global_show class is also set.
*/
.ctb_global_show .ctb_show.ctb_hideshow {
  display: block;
}
.ctb_global_show .ctb_show + .input_area,
.ctb_global_show .ctb_show + div.text_cell_input,
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border-top-right-radius: 0px;
  border-top-left-radius: 0px;
}
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border: 1px solid #cfcfcf;
}
.celltoolbar {
  font-size: 87%;
  padding-top: 3px;
}
.celltoolbar select {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
  width: inherit;
  font-size: inherit;
  height: 22px;
  padding: 0px;
  display: inline-block;
}
.celltoolbar select:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.celltoolbar select::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.celltoolbar select:-ms-input-placeholder {
  color: #999;
}
.celltoolbar select::-webkit-input-placeholder {
  color: #999;
}
.celltoolbar select::-ms-expand {
  border: 0;
  background-color: transparent;
}
.celltoolbar select[disabled],
.celltoolbar select[readonly],
fieldset[disabled] .celltoolbar select {
  background-color: #eeeeee;
  opacity: 1;
}
.celltoolbar select[disabled],
fieldset[disabled] .celltoolbar select {
  cursor: not-allowed;
}
textarea.celltoolbar select {
  height: auto;
}
select.celltoolbar select {
  height: 30px;
  line-height: 30px;
}
textarea.celltoolbar select,
select[multiple].celltoolbar select {
  height: auto;
}
.celltoolbar label {
  margin-left: 5px;
  margin-right: 5px;
}
.tags_button_container {
  width: 100%;
  display: flex;
}
.tag-container {
  display: flex;
  flex-direction: row;
  flex-grow: 1;
  overflow: hidden;
  position: relative;
}
.tag-container > * {
  margin: 0 4px;
}
.remove-tag-btn {
  margin-left: 4px;
}
.tags-input {
  display: flex;
}
.cell-tag:last-child:after {
  content: "";
  position: absolute;
  right: 0;
  width: 40px;
  height: 100%;
  /* Fade to background color of cell toolbar */
  background: linear-gradient(to right, rgba(0, 0, 0, 0), #EEE);
}
.tags-input > * {
  margin-left: 4px;
}
.cell-tag,
.tags-input input,
.tags-input button {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
  box-shadow: none;
  width: inherit;
  font-size: inherit;
  height: 22px;
  line-height: 22px;
  padding: 0px 4px;
  display: inline-block;
}
.cell-tag:focus,
.tags-input input:focus,
.tags-input button:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.cell-tag::-moz-placeholder,
.tags-input input::-moz-placeholder,
.tags-input button::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.cell-tag:-ms-input-placeholder,
.tags-input input:-ms-input-placeholder,
.tags-input button:-ms-input-placeholder {
  color: #999;
}
.cell-tag::-webkit-input-placeholder,
.tags-input input::-webkit-input-placeholder,
.tags-input button::-webkit-input-placeholder {
  color: #999;
}
.cell-tag::-ms-expand,
.tags-input input::-ms-expand,
.tags-input button::-ms-expand {
  border: 0;
  background-color: transparent;
}
.cell-tag[disabled],
.tags-input input[disabled],
.tags-input button[disabled],
.cell-tag[readonly],
.tags-input input[readonly],
.tags-input button[readonly],
fieldset[disabled] .cell-tag,
fieldset[disabled] .tags-input input,
fieldset[disabled] .tags-input button {
  background-color: #eeeeee;
  opacity: 1;
}
.cell-tag[disabled],
.tags-input input[disabled],
.tags-input button[disabled],
fieldset[disabled] .cell-tag,
fieldset[disabled] .tags-input input,
fieldset[disabled] .tags-input button {
  cursor: not-allowed;
}
textarea.cell-tag,
textarea.tags-input input,
textarea.tags-input button {
  height: auto;
}
select.cell-tag,
select.tags-input input,
select.tags-input button {
  height: 30px;
  line-height: 30px;
}
textarea.cell-tag,
textarea.tags-input input,
textarea.tags-input button,
select[multiple].cell-tag,
select[multiple].tags-input input,
select[multiple].tags-input button {
  height: auto;
}
.cell-tag,
.tags-input button {
  padding: 0px 4px;
}
.cell-tag {
  background-color: #fff;
  white-space: nowrap;
}
.tags-input input[type=text]:focus {
  outline: none;
  box-shadow: none;
  border-color: #ccc;
}
.completions {
  position: absolute;
  z-index: 110;
  overflow: hidden;
  border: 1px solid #ababab;
  border-radius: 2px;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  line-height: 1;
}
.completions select {
  background: white;
  outline: none;
  border: none;
  padding: 0px;
  margin: 0px;
  overflow: auto;
  font-family: monospace;
  font-size: 110%;
  color: #000;
  width: auto;
}
.completions select option.context {
  color: #286090;
}
#kernel_logo_widget .current_kernel_logo {
  display: none;
  margin-top: -1px;
  margin-bottom: -1px;
  width: 32px;
  height: 32px;
}
[dir="rtl"] #kernel_logo_widget {
  float: left !important;
  float: left;
}
.modal .modal-body .move-path {
  display: flex;
  flex-direction: row;
  justify-content: space;
  align-items: center;
}
.modal .modal-body .move-path .server-root {
  padding-right: 20px;
}
.modal .modal-body .move-path .path-input {
  flex: 1;
}
#menubar {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  margin-top: 1px;
}
#menubar .navbar {
  border-top: 1px;
  border-radius: 0px 0px 2px 2px;
  margin-bottom: 0px;
}
#menubar .navbar-toggle {
  float: left;
  padding-top: 7px;
  padding-bottom: 7px;
  border: none;
}
#menubar .navbar-collapse {
  clear: left;
}
[dir="rtl"] #menubar .navbar-toggle {
  float: right;
}
[dir="rtl"] #menubar .navbar-collapse {
  clear: right;
}
[dir="rtl"] #menubar .navbar-nav {
  float: right;
}
[dir="rtl"] #menubar .nav {
  padding-right: 0px;
}
[dir="rtl"] #menubar .navbar-nav > li {
  float: right;
}
[dir="rtl"] #menubar .navbar-right {
  float: left !important;
}
[dir="rtl"] ul.dropdown-menu {
  text-align: right;
  left: auto;
}
[dir="rtl"] ul#new-menu.dropdown-menu {
  right: auto;
  left: 0;
}
.nav-wrapper {
  border-bottom: 1px solid #e7e7e7;
}
i.menu-icon {
  padding-top: 4px;
}
[dir="rtl"] i.menu-icon.pull-right {
  float: left !important;
  float: left;
}
ul#help_menu li a {
  overflow: hidden;
  padding-right: 2.2em;
}
ul#help_menu li a i {
  margin-right: -1.2em;
}
[dir="rtl"] ul#help_menu li a {
  padding-left: 2.2em;
}
[dir="rtl"] ul#help_menu li a i {
  margin-right: 0;
  margin-left: -1.2em;
}
[dir="rtl"] ul#help_menu li a i.pull-right {
  float: left !important;
  float: left;
}
.dropdown-submenu {
  position: relative;
}
.dropdown-submenu > .dropdown-menu {
  top: 0;
  left: 100%;
  margin-top: -6px;
  margin-left: -1px;
}
[dir="rtl"] .dropdown-submenu > .dropdown-menu {
  right: 100%;
  margin-right: -1px;
}
.dropdown-submenu:hover > .dropdown-menu {
  display: block;
}
.dropdown-submenu > a:after {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: block;
  content: "\f0da";
  float: right;
  color: #333333;
  margin-top: 2px;
  margin-right: -10px;
}
.dropdown-submenu > a:after.fa-pull-left {
  margin-right: .3em;
}
.dropdown-submenu > a:after.fa-pull-right {
  margin-left: .3em;
}
.dropdown-submenu > a:after.pull-left {
  margin-right: .3em;
}
.dropdown-submenu > a:after.pull-right {
  margin-left: .3em;
}
[dir="rtl"] .dropdown-submenu > a:after {
  float: left;
  content: "\f0d9";
  margin-right: 0;
  margin-left: -10px;
}
.dropdown-submenu:hover > a:after {
  color: #262626;
}
.dropdown-submenu.pull-left {
  float: none;
}
.dropdown-submenu.pull-left > .dropdown-menu {
  left: -100%;
  margin-left: 10px;
}
#notification_area {
  float: right !important;
  float: right;
  z-index: 10;
}
[dir="rtl"] #notification_area {
  float: left !important;
  float: left;
}
.indicator_area {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
[dir="rtl"] .indicator_area {
  float: left !important;
  float: left;
}
#kernel_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  border-left: 1px solid;
}
#kernel_indicator .kernel_indicator_name {
  padding-left: 5px;
  padding-right: 5px;
}
[dir="rtl"] #kernel_indicator {
  float: left !important;
  float: left;
  border-left: 0;
  border-right: 1px solid;
}
#modal_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
[dir="rtl"] #modal_indicator {
  float: left !important;
  float: left;
}
#readonly-indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  margin-top: 2px;
  margin-bottom: 0px;
  margin-left: 0px;
  margin-right: 0px;
  display: none;
}
.modal_indicator:before {
  width: 1.28571429em;
  text-align: center;
}
.edit_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f040";
}
.edit_mode .modal_indicator:before.fa-pull-left {
  margin-right: .3em;
}
.edit_mode .modal_indicator:before.fa-pull-right {
  margin-left: .3em;
}
.edit_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.edit_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.command_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: ' ';
}
.command_mode .modal_indicator:before.fa-pull-left {
  margin-right: .3em;
}
.command_mode .modal_indicator:before.fa-pull-right {
  margin-left: .3em;
}
.command_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.command_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.kernel_idle_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f10c";
}
.kernel_idle_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_idle_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_idle_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_idle_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_busy_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f111";
}
.kernel_busy_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_busy_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_busy_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_busy_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_dead_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f1e2";
}
.kernel_dead_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_dead_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_dead_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_dead_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_disconnected_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f127";
}
.kernel_disconnected_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_disconnected_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_disconnected_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_disconnected_icon:before.pull-right {
  margin-left: .3em;
}
.notification_widget {
  color: #777;
  z-index: 10;
  background: rgba(240, 240, 240, 0.5);
  margin-right: 4px;
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget:focus,
.notification_widget.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.notification_widget:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active:hover,
.notification_widget.active:hover,
.open > .dropdown-toggle.notification_widget:hover,
.notification_widget:active:focus,
.notification_widget.active:focus,
.open > .dropdown-toggle.notification_widget:focus,
.notification_widget:active.focus,
.notification_widget.active.focus,
.open > .dropdown-toggle.notification_widget.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  background-image: none;
}
.notification_widget.disabled:hover,
.notification_widget[disabled]:hover,
fieldset[disabled] .notification_widget:hover,
.notification_widget.disabled:focus,
.notification_widget[disabled]:focus,
fieldset[disabled] .notification_widget:focus,
.notification_widget.disabled.focus,
.notification_widget[disabled].focus,
fieldset[disabled] .notification_widget.focus {
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget .badge {
  color: #fff;
  background-color: #333;
}
.notification_widget.warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning:focus,
.notification_widget.warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.notification_widget.warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active:hover,
.notification_widget.warning.active:hover,
.open > .dropdown-toggle.notification_widget.warning:hover,
.notification_widget.warning:active:focus,
.notification_widget.warning.active:focus,
.open > .dropdown-toggle.notification_widget.warning:focus,
.notification_widget.warning:active.focus,
.notification_widget.warning.active.focus,
.open > .dropdown-toggle.notification_widget.warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  background-image: none;
}
.notification_widget.warning.disabled:hover,
.notification_widget.warning[disabled]:hover,
fieldset[disabled] .notification_widget.warning:hover,
.notification_widget.warning.disabled:focus,
.notification_widget.warning[disabled]:focus,
fieldset[disabled] .notification_widget.warning:focus,
.notification_widget.warning.disabled.focus,
.notification_widget.warning[disabled].focus,
fieldset[disabled] .notification_widget.warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.notification_widget.success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success:focus,
.notification_widget.success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.notification_widget.success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active:hover,
.notification_widget.success.active:hover,
.open > .dropdown-toggle.notification_widget.success:hover,
.notification_widget.success:active:focus,
.notification_widget.success.active:focus,
.open > .dropdown-toggle.notification_widget.success:focus,
.notification_widget.success:active.focus,
.notification_widget.success.active.focus,
.open > .dropdown-toggle.notification_widget.success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  background-image: none;
}
.notification_widget.success.disabled:hover,
.notification_widget.success[disabled]:hover,
fieldset[disabled] .notification_widget.success:hover,
.notification_widget.success.disabled:focus,
.notification_widget.success[disabled]:focus,
fieldset[disabled] .notification_widget.success:focus,
.notification_widget.success.disabled.focus,
.notification_widget.success[disabled].focus,
fieldset[disabled] .notification_widget.success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.notification_widget.info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info:focus,
.notification_widget.info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.notification_widget.info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active:hover,
.notification_widget.info.active:hover,
.open > .dropdown-toggle.notification_widget.info:hover,
.notification_widget.info:active:focus,
.notification_widget.info.active:focus,
.open > .dropdown-toggle.notification_widget.info:focus,
.notification_widget.info:active.focus,
.notification_widget.info.active.focus,
.open > .dropdown-toggle.notification_widget.info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  background-image: none;
}
.notification_widget.info.disabled:hover,
.notification_widget.info[disabled]:hover,
fieldset[disabled] .notification_widget.info:hover,
.notification_widget.info.disabled:focus,
.notification_widget.info[disabled]:focus,
fieldset[disabled] .notification_widget.info:focus,
.notification_widget.info.disabled.focus,
.notification_widget.info[disabled].focus,
fieldset[disabled] .notification_widget.info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.notification_widget.danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger:focus,
.notification_widget.danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.notification_widget.danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active:hover,
.notification_widget.danger.active:hover,
.open > .dropdown-toggle.notification_widget.danger:hover,
.notification_widget.danger:active:focus,
.notification_widget.danger.active:focus,
.open > .dropdown-toggle.notification_widget.danger:focus,
.notification_widget.danger:active.focus,
.notification_widget.danger.active.focus,
.open > .dropdown-toggle.notification_widget.danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  background-image: none;
}
.notification_widget.danger.disabled:hover,
.notification_widget.danger[disabled]:hover,
fieldset[disabled] .notification_widget.danger:hover,
.notification_widget.danger.disabled:focus,
.notification_widget.danger[disabled]:focus,
fieldset[disabled] .notification_widget.danger:focus,
.notification_widget.danger.disabled.focus,
.notification_widget.danger[disabled].focus,
fieldset[disabled] .notification_widget.danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger .badge {
  color: #d9534f;
  background-color: #fff;
}
div#pager {
  background-color: #fff;
  font-size: 14px;
  line-height: 20px;
  overflow: hidden;
  display: none;
  position: fixed;
  bottom: 0px;
  width: 100%;
  max-height: 50%;
  padding-top: 8px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  /* Display over codemirror */
  z-index: 100;
  /* Hack which prevents jquery ui resizable from changing top. */
  top: auto !important;
}
div#pager pre {
  line-height: 1.21429em;
  color: #000;
  background-color: #f7f7f7;
  padding: 0.4em;
}
div#pager #pager-button-area {
  position: absolute;
  top: 8px;
  right: 20px;
}
div#pager #pager-contents {
  position: relative;
  overflow: auto;
  width: 100%;
  height: 100%;
}
div#pager #pager-contents #pager-container {
  position: relative;
  padding: 15px 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
div#pager .ui-resizable-handle {
  top: 0px;
  height: 8px;
  background: #f7f7f7;
  border-top: 1px solid #cfcfcf;
  border-bottom: 1px solid #cfcfcf;
  /* This injects handle bars (a short, wide = symbol) for 
        the resize handle. */
}
div#pager .ui-resizable-handle::after {
  content: '';
  top: 2px;
  left: 50%;
  height: 3px;
  width: 30px;
  margin-left: -15px;
  position: absolute;
  border-top: 1px solid #cfcfcf;
}
.quickhelp {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  line-height: 1.8em;
}
.shortcut_key {
  display: inline-block;
  width: 21ex;
  text-align: right;
  font-family: monospace;
}
.shortcut_descr {
  display: inline-block;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
span.save_widget {
  height: 30px;
  margin-top: 4px;
  display: flex;
  justify-content: flex-start;
  align-items: baseline;
  width: 50%;
  flex: 1;
}
span.save_widget span.filename {
  height: 100%;
  line-height: 1em;
  margin-left: 16px;
  border: none;
  font-size: 146.5%;
  text-overflow: ellipsis;
  overflow: hidden;
  white-space: nowrap;
  border-radius: 2px;
}
span.save_widget span.filename:hover {
  background-color: #e6e6e6;
}
[dir="rtl"] span.save_widget.pull-left {
  float: right !important;
  float: right;
}
[dir="rtl"] span.save_widget span.filename {
  margin-left: 0;
  margin-right: 16px;
}
span.checkpoint_status,
span.autosave_status {
  font-size: small;
  white-space: nowrap;
  padding: 0 5px;
}
@media (max-width: 767px) {
  span.save_widget {
    font-size: small;
    padding: 0 0 0 5px;
  }
  span.checkpoint_status,
  span.autosave_status {
    display: none;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  span.checkpoint_status {
    display: none;
  }
  span.autosave_status {
    font-size: x-small;
  }
}
.toolbar {
  padding: 0px;
  margin-left: -5px;
  margin-top: 2px;
  margin-bottom: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.toolbar select,
.toolbar label {
  width: auto;
  vertical-align: middle;
  margin-right: 2px;
  margin-bottom: 0px;
  display: inline;
  font-size: 92%;
  margin-left: 0.3em;
  margin-right: 0.3em;
  padding: 0px;
  padding-top: 3px;
}
.toolbar .btn {
  padding: 2px 8px;
}
.toolbar .btn-group {
  margin-top: 0px;
  margin-left: 5px;
}
.toolbar-btn-label {
  margin-left: 6px;
}
#maintoolbar {
  margin-bottom: -3px;
  margin-top: -8px;
  border: 0px;
  min-height: 27px;
  margin-left: 0px;
  padding-top: 11px;
  padding-bottom: 3px;
}
#maintoolbar .navbar-text {
  float: none;
  vertical-align: middle;
  text-align: right;
  margin-left: 5px;
  margin-right: 0px;
  margin-top: 0px;
}
.select-xs {
  height: 24px;
}
[dir="rtl"] .btn-group > .btn,
.btn-group-vertical > .btn {
  float: right;
}
.pulse,
.dropdown-menu > li > a.pulse,
li.pulse > a.dropdown-toggle,
li.pulse.open > a.dropdown-toggle {
  background-color: #F37626;
  color: white;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
/** WARNING IF YOU ARE EDITTING THIS FILE, if this is a .css file, It has a lot
 * of chance of beeing generated from the ../less/[samename].less file, you can
 * try to get back the less file by reverting somme commit in history
 **/
/*
 * We'll try to get something pretty, so we
 * have some strange css to have the scroll bar on
 * the left with fix button on the top right of the tooltip
 */
@-moz-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-webkit-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-moz-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
@-webkit-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
/*properties of tooltip after "expand"*/
.bigtooltip {
  overflow: auto;
  height: 200px;
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
}
/*properties of tooltip before "expand"*/
.smalltooltip {
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
  text-overflow: ellipsis;
  overflow: hidden;
  height: 80px;
}
.tooltipbuttons {
  position: absolute;
  padding-right: 15px;
  top: 0px;
  right: 0px;
}
.tooltiptext {
  /*avoid the button to overlap on some docstring*/
  padding-right: 30px;
}
.ipython_tooltip {
  max-width: 700px;
  /*fade-in animation when inserted*/
  -webkit-animation: fadeOut 400ms;
  -moz-animation: fadeOut 400ms;
  animation: fadeOut 400ms;
  -webkit-animation: fadeIn 400ms;
  -moz-animation: fadeIn 400ms;
  animation: fadeIn 400ms;
  vertical-align: middle;
  background-color: #f7f7f7;
  overflow: visible;
  border: #ababab 1px solid;
  outline: none;
  padding: 3px;
  margin: 0px;
  padding-left: 7px;
  font-family: monospace;
  min-height: 50px;
  -moz-box-shadow: 0px 6px 10px -1px #adadad;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  border-radius: 2px;
  position: absolute;
  z-index: 1000;
}
.ipython_tooltip a {
  float: right;
}
.ipython_tooltip .tooltiptext pre {
  border: 0;
  border-radius: 0;
  font-size: 100%;
  background-color: #f7f7f7;
}
.pretooltiparrow {
  left: 0px;
  margin: 0px;
  top: -16px;
  width: 40px;
  height: 16px;
  overflow: hidden;
  position: absolute;
}
.pretooltiparrow:before {
  background-color: #f7f7f7;
  border: 1px #ababab solid;
  z-index: 11;
  content: "";
  position: absolute;
  left: 15px;
  top: 10px;
  width: 25px;
  height: 25px;
  -webkit-transform: rotate(45deg);
  -moz-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  -o-transform: rotate(45deg);
}
ul.typeahead-list i {
  margin-left: -10px;
  width: 18px;
}
[dir="rtl"] ul.typeahead-list i {
  margin-left: 0;
  margin-right: -10px;
}
ul.typeahead-list {
  max-height: 80vh;
  overflow: auto;
}
ul.typeahead-list > li > a {
  /** Firefox bug **/
  /* see https://github.com/jupyter/notebook/issues/559 */
  white-space: normal;
}
ul.typeahead-list  > li > a.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .typeahead-list {
  text-align: right;
}
.cmd-palette .modal-body {
  padding: 7px;
}
.cmd-palette form {
  background: white;
}
.cmd-palette input {
  outline: none;
}
.no-shortcut {
  min-width: 20px;
  color: transparent;
}
[dir="rtl"] .no-shortcut.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .command-shortcut.pull-right {
  float: left !important;
  float: left;
}
.command-shortcut:before {
  content: "(command mode)";
  padding-right: 3px;
  color: #777777;
}
.edit-shortcut:before {
  content: "(edit)";
  padding-right: 3px;
  color: #777777;
}
[dir="rtl"] .edit-shortcut.pull-right {
  float: left !important;
  float: left;
}
#find-and-replace #replace-preview .match,
#find-and-replace #replace-preview .insert {
  background-color: #BBDEFB;
  border-color: #90CAF9;
  border-style: solid;
  border-width: 1px;
  border-radius: 0px;
}
[dir="ltr"] #find-and-replace .input-group-btn + .form-control {
  border-left: none;
}
[dir="rtl"] #find-and-replace .input-group-btn + .form-control {
  border-right: none;
}
#find-and-replace #replace-preview .replace .match {
  background-color: #FFCDD2;
  border-color: #EF9A9A;
  border-radius: 0px;
}
#find-and-replace #replace-preview .replace .insert {
  background-color: #C8E6C9;
  border-color: #A5D6A7;
  border-radius: 0px;
}
#find-and-replace #replace-preview {
  max-height: 60vh;
  overflow: auto;
}
#find-and-replace #replace-preview pre {
  padding: 5px 10px;
}
.terminal-app {
  background: #EEE;
}
.terminal-app #header {
  background: #fff;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.terminal-app .terminal {
  width: 100%;
  float: left;
  font-family: monospace;
  color: white;
  background: black;
  padding: 0.4em;
  border-radius: 2px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
}
.terminal-app .terminal,
.terminal-app .terminal dummy-screen {
  line-height: 1em;
  font-size: 14px;
}
.terminal-app .terminal .xterm-rows {
  padding: 10px;
}
.terminal-app .terminal-cursor {
  color: black;
  background: white;
}
.terminal-app #terminado-container {
  margin-top: 20px;
}
/*# sourceMappingURL=style.min.css.map */
    </style>
<style type="text/css">
    .highlight .hll { background-color: #ffffcc }
.highlight  { background: #f8f8f8; }
.highlight .c { color: #408080; font-style: italic } /* Comment */
.highlight .err { border: 1px solid #FF0000 } /* Error */
.highlight .k { color: #008000; font-weight: bold } /* Keyword */
.highlight .o { color: #666666 } /* Operator */
.highlight .ch { color: #408080; font-style: italic } /* Comment.Hashbang */
.highlight .cm { color: #408080; font-style: italic } /* Comment.Multiline */
.highlight .cp { color: #BC7A00 } /* Comment.Preproc */
.highlight .cpf { color: #408080; font-style: italic } /* Comment.PreprocFile */
.highlight .c1 { color: #408080; font-style: italic } /* Comment.Single */
.highlight .cs { color: #408080; font-style: italic } /* Comment.Special */
.highlight .gd { color: #A00000 } /* Generic.Deleted */
.highlight .ge { font-style: italic } /* Generic.Emph */
.highlight .gr { color: #FF0000 } /* Generic.Error */
.highlight .gh { color: #000080; font-weight: bold } /* Generic.Heading */
.highlight .gi { color: #00A000 } /* Generic.Inserted */
.highlight .go { color: #888888 } /* Generic.Output */
.highlight .gp { color: #000080; font-weight: bold } /* Generic.Prompt */
.highlight .gs { font-weight: bold } /* Generic.Strong */
.highlight .gu { color: #800080; font-weight: bold } /* Generic.Subheading */
.highlight .gt { color: #0044DD } /* Generic.Traceback */
.highlight .kc { color: #008000; font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: #008000; font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: #008000; font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: #008000 } /* Keyword.Pseudo */
.highlight .kr { color: #008000; font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: #B00040 } /* Keyword.Type */
.highlight .m { color: #666666 } /* Literal.Number */
.highlight .s { color: #BA2121 } /* Literal.String */
.highlight .na { color: #7D9029 } /* Name.Attribute */
.highlight .nb { color: #008000 } /* Name.Builtin */
.highlight .nc { color: #0000FF; font-weight: bold } /* Name.Class */
.highlight .no { color: #880000 } /* Name.Constant */
.highlight .nd { color: #AA22FF } /* Name.Decorator */
.highlight .ni { color: #999999; font-weight: bold } /* Name.Entity */
.highlight .ne { color: #D2413A; font-weight: bold } /* Name.Exception */
.highlight .nf { color: #0000FF } /* Name.Function */
.highlight .nl { color: #A0A000 } /* Name.Label */
.highlight .nn { color: #0000FF; font-weight: bold } /* Name.Namespace */
.highlight .nt { color: #008000; font-weight: bold } /* Name.Tag */
.highlight .nv { color: #19177C } /* Name.Variable */
.highlight .ow { color: #AA22FF; font-weight: bold } /* Operator.Word */
.highlight .w { color: #bbbbbb } /* Text.Whitespace */
.highlight .mb { color: #666666 } /* Literal.Number.Bin */
.highlight .mf { color: #666666 } /* Literal.Number.Float */
.highlight .mh { color: #666666 } /* Literal.Number.Hex */
.highlight .mi { color: #666666 } /* Literal.Number.Integer */
.highlight .mo { color: #666666 } /* Literal.Number.Oct */
.highlight .sa { color: #BA2121 } /* Literal.String.Affix */
.highlight .sb { color: #BA2121 } /* Literal.String.Backtick */
.highlight .sc { color: #BA2121 } /* Literal.String.Char */
.highlight .dl { color: #BA2121 } /* Literal.String.Delimiter */
.highlight .sd { color: #BA2121; font-style: italic } /* Literal.String.Doc */
.highlight .s2 { color: #BA2121 } /* Literal.String.Double */
.highlight .se { color: #BB6622; font-weight: bold } /* Literal.String.Escape */
.highlight .sh { color: #BA2121 } /* Literal.String.Heredoc */
.highlight .si { color: #BB6688; font-weight: bold } /* Literal.String.Interpol */
.highlight .sx { color: #008000 } /* Literal.String.Other */
.highlight .sr { color: #BB6688 } /* Literal.String.Regex */
.highlight .s1 { color: #BA2121 } /* Literal.String.Single */
.highlight .ss { color: #19177C } /* Literal.String.Symbol */
.highlight .bp { color: #008000 } /* Name.Builtin.Pseudo */
.highlight .fm { color: #0000FF } /* Name.Function.Magic */
.highlight .vc { color: #19177C } /* Name.Variable.Class */
.highlight .vg { color: #19177C } /* Name.Variable.Global */
.highlight .vi { color: #19177C } /* Name.Variable.Instance */
.highlight .vm { color: #19177C } /* Name.Variable.Magic */
.highlight .il { color: #666666 } /* Literal.Number.Integer.Long */
    </style>
<style type="text/css">
    /*This file contains any manual css for this page that needs to override the global styles.
This is only required when different pages style the same element differently. This is just
a hack to deal with our current css styles and no new styling should be added in this file.*/

#ipython-main-app {
    position: relative;
}
#jupyter-main-app {
    position: relative;
}

    </style>


<style type="text/css">
/* Overrides of notebook CSS for static HTML export */
body {
  overflow: visible;
  padding: 8px;
}

div#notebook {
  overflow: visible;
  border-top: none;
}@media print {
  div.cell {
    display: block;
    page-break-inside: avoid;
  } 
  div.output_wrapper { 
    display: block;
    page-break-inside: avoid; 
  }
  div.output { 
    display: block;
    page-break-inside: avoid; 
  }
}
</style>

<!-- Custom stylesheet, it must be in the same directory as the html file -->
<link rel="stylesheet" href="custom.css">

<!-- Loading mathjax macro -->
<!-- Load mathjax -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/latest.js?config=TeX-AMS_HTML"></script>
    <!-- MathJax configuration -->
    <script type="text/x-mathjax-config">
    MathJax.Hub.Config({
        tex2jax: {
            inlineMath: [ ['$','$'], ["\\(","\\)"] ],
            displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
            processEscapes: true,
            processEnvironments: true
        },
        // Center justify equations in code and markdown cells. Elsewhere
        // we use CSS to left justify single line equations in code cells.
        displayAlign: 'center',
        "HTML-CSS": {
            styles: {'.MathJax_Display': {"margin": 0}},
            linebreaks: { automatic: true }
        }
    });
    </script>
    <!-- End of mathjax configuration --></head>
<body>
  <div tabindex="-1" id="notebook" class="border-box-sizing">
    <div class="container" id="notebook-container">

<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Case-Study:-Breast-Cancer-Detection">Case Study: Breast Cancer Detection<a class="anchor-link" href="#Case-Study:-Breast-Cancer-Detection">¶</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p></p><h1>Table of Contents<span class="tocSkip"></span></h1>
<div class="toc"><ul class="toc-item"><li><span><a href="#Case-Study:-Breast-Cancer-Detection" data-toc-modified-id="Case-Study:-Breast-Cancer-Detection-1"><span class="toc-item-num">1  </span>Case Study: Breast Cancer Detection</a></span></li><li><span><a href="#Introduction" data-toc-modified-id="Introduction-2"><span class="toc-item-num">2  </span>Introduction</a></span></li><li><span><a href="#Libraries-and-dataset-importation" data-toc-modified-id="Libraries-and-dataset-importation-3"><span class="toc-item-num">3  </span>Libraries and dataset importation</a></span></li><li><span><a href="#Data-exploration" data-toc-modified-id="Data-exploration-4"><span class="toc-item-num">4  </span>Data exploration</a></span></li><li><span><a href="#Data-visualization" data-toc-modified-id="Data-visualization-5"><span class="toc-item-num">5  </span>Data visualization</a></span></li><li><span><a href="#Data-pre-processing" data-toc-modified-id="Data-pre-processing-6"><span class="toc-item-num">6  </span>Data pre-processing</a></span></li><li><span><a href="#Model-creation" data-toc-modified-id="Model-creation-7"><span class="toc-item-num">7  </span>Model creation</a></span></li><li><span><a href="#Model-evaluation" data-toc-modified-id="Model-evaluation-8"><span class="toc-item-num">8  </span>Model evaluation</a></span></li><li><span><a href="#Conlusion" data-toc-modified-id="Conlusion-9"><span class="toc-item-num">9  </span>Conlusion</a></span></li></ul></div>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Introduction">Introduction<a class="anchor-link" href="#Introduction">¶</a></h1><p>Breast cancer is one of the most common cancer among women worldwide accounting for 25 percent of all cancer cases and affected 2.1 million people in 2015, with early diagnosis, they could significantly increases their chances of survival.The key challenge in cancer detection is how to classify tumors into malignant or benign. Machine learning techniques can dramatically improves the accuracy of diagnosis.</p>
<p>Research indicates that most experienced physicians can diagnose cancer with 79 percent accuracy while 91 percent correct diagnosis is achieved using machine learning techniques.So the first step in the cancer diagnosis process is to do what we call final needle aspirate or any process which is simply extracting some of the cells out of the tumor. And at that stage we don't know if that human is malignant or benign.</p>
<p>When we say benign that means that the tumor is kind of not spreading across the bodies of the patient and is safe somehow. if it's malignant that means it's cancerous that we need to intervene and actually stop the cancer growth. The idea is we want to teach the machine how to basically classify images or classify data and tell us if it's malignant or benign. for example. in this case without any human intervention.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><strong>Probem</strong>:</p>
<ul>
<li>Predict if the cancer diagnosis is benign or malignant based on several observations/features</li>
</ul>
<p><strong>Dataset</strong>:</p>
<ul>
<li>Radius (mean of distances from center to points on the perimeter)</li>
<li>Texture (standard deviation of gray-scale values)</li>
<li>Perimeter</li>
<li>Area</li>
<li>Smoothness (local variation in radius lengths)</li>
<li>Compactness (perimeter^2 / area - 1.0)</li>
<li>Concavity (severity of concave portions of the contour)</li>
<li>Concave points (number of concave portions of the contour)</li>
<li>Symmetry </li>
<li>Fractal dimension ("coastline approximation" - 1)</li>
</ul>
<p><strong>Source:</strong> <a href="https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+(Diagnostic">https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+(Diagnostic</a>)</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Libraries-and-dataset-importation">Libraries and dataset importation<a class="anchor-link" href="#Libraries-and-dataset-importation">¶</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [1]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Import libraries</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
<span class="kn">import</span> <span class="nn">pandas</span> <span class="k">as</span> <span class="nn">pd</span>
<span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">plt</span>
<span class="kn">import</span> <span class="nn">seaborn</span> <span class="k">as</span> <span class="nn">sns</span>
<span class="n">sns</span><span class="o">.</span><span class="n">set</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [2]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Import Cancer data drom the Sklearn library</span>
<span class="kn">from</span> <span class="nn">sklearn.datasets</span> <span class="kn">import</span> <span class="n">load_breast_cancer</span>
<span class="n">cancer</span> <span class="o">=</span> <span class="n">load_breast_cancer</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Data-exploration">Data exploration<a class="anchor-link" href="#Data-exploration">¶</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [3]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Check cancer dictionaries</span>
<span class="n">cancer</span><span class="o">.</span><span class="n">keys</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[3]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>dict_keys(['data', 'target', 'frame', 'target_names', 'DESCR', 'feature_names', 'filename'])</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [4]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Target</span>
<span class="nb">print</span><span class="p">(</span><span class="n">cancer</span><span class="p">[</span><span class="s1">'target_names'</span><span class="p">])</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>['malignant' 'benign']
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [5]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Features</span>
<span class="nb">print</span><span class="p">(</span><span class="n">cancer</span><span class="p">[</span><span class="s1">'feature_names'</span><span class="p">])</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>['mean radius' 'mean texture' 'mean perimeter' 'mean area'
 'mean smoothness' 'mean compactness' 'mean concavity'
 'mean concave points' 'mean symmetry' 'mean fractal dimension'
 'radius error' 'texture error' 'perimeter error' 'area error'
 'smoothness error' 'compactness error' 'concavity error'
 'concave points error' 'symmetry error' 'fractal dimension error'
 'worst radius' 'worst texture' 'worst perimeter' 'worst area'
 'worst smoothness' 'worst compactness' 'worst concavity'
 'worst concave points' 'worst symmetry' 'worst fractal dimension']
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [6]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Create dataframe</span>
<span class="n">df_cancer</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">c_</span><span class="p">[</span><span class="n">cancer</span><span class="p">[</span><span class="s1">'data'</span><span class="p">],</span> <span class="n">cancer</span><span class="p">[</span><span class="s1">'target'</span><span class="p">]],</span> <span class="n">columns</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">cancer</span><span class="p">[</span><span class="s1">'feature_names'</span><span class="p">],</span> <span class="p">[</span><span class="s1">'target'</span><span class="p">]))</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [7]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Analyze dataset</span>
<span class="n">df_cancer</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[7]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>mean radius</th>
      <th>mean texture</th>
      <th>mean perimeter</th>
      <th>mean area</th>
      <th>mean smoothness</th>
      <th>mean compactness</th>
      <th>mean concavity</th>
      <th>mean concave points</th>
      <th>mean symmetry</th>
      <th>mean fractal dimension</th>
      <th>...</th>
      <th>worst texture</th>
      <th>worst perimeter</th>
      <th>worst area</th>
      <th>worst smoothness</th>
      <th>worst compactness</th>
      <th>worst concavity</th>
      <th>worst concave points</th>
      <th>worst symmetry</th>
      <th>worst fractal dimension</th>
      <th>target</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>17.99</td>
      <td>10.38</td>
      <td>122.80</td>
      <td>1001.0</td>
      <td>0.11840</td>
      <td>0.27760</td>
      <td>0.3001</td>
      <td>0.14710</td>
      <td>0.2419</td>
      <td>0.07871</td>
      <td>...</td>
      <td>17.33</td>
      <td>184.60</td>
      <td>2019.0</td>
      <td>0.1622</td>
      <td>0.6656</td>
      <td>0.7119</td>
      <td>0.2654</td>
      <td>0.4601</td>
      <td>0.11890</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>20.57</td>
      <td>17.77</td>
      <td>132.90</td>
      <td>1326.0</td>
      <td>0.08474</td>
      <td>0.07864</td>
      <td>0.0869</td>
      <td>0.07017</td>
      <td>0.1812</td>
      <td>0.05667</td>
      <td>...</td>
      <td>23.41</td>
      <td>158.80</td>
      <td>1956.0</td>
      <td>0.1238</td>
      <td>0.1866</td>
      <td>0.2416</td>
      <td>0.1860</td>
      <td>0.2750</td>
      <td>0.08902</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>19.69</td>
      <td>21.25</td>
      <td>130.00</td>
      <td>1203.0</td>
      <td>0.10960</td>
      <td>0.15990</td>
      <td>0.1974</td>
      <td>0.12790</td>
      <td>0.2069</td>
      <td>0.05999</td>
      <td>...</td>
      <td>25.53</td>
      <td>152.50</td>
      <td>1709.0</td>
      <td>0.1444</td>
      <td>0.4245</td>
      <td>0.4504</td>
      <td>0.2430</td>
      <td>0.3613</td>
      <td>0.08758</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>11.42</td>
      <td>20.38</td>
      <td>77.58</td>
      <td>386.1</td>
      <td>0.14250</td>
      <td>0.28390</td>
      <td>0.2414</td>
      <td>0.10520</td>
      <td>0.2597</td>
      <td>0.09744</td>
      <td>...</td>
      <td>26.50</td>
      <td>98.87</td>
      <td>567.7</td>
      <td>0.2098</td>
      <td>0.8663</td>
      <td>0.6869</td>
      <td>0.2575</td>
      <td>0.6638</td>
      <td>0.17300</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>20.29</td>
      <td>14.34</td>
      <td>135.10</td>
      <td>1297.0</td>
      <td>0.10030</td>
      <td>0.13280</td>
      <td>0.1980</td>
      <td>0.10430</td>
      <td>0.1809</td>
      <td>0.05883</td>
      <td>...</td>
      <td>16.67</td>
      <td>152.20</td>
      <td>1575.0</td>
      <td>0.1374</td>
      <td>0.2050</td>
      <td>0.4000</td>
      <td>0.1625</td>
      <td>0.2364</td>
      <td>0.07678</td>
      <td>0.0</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 31 columns</p>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [8]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Analyze dataset</span>
<span class="n">df_cancer</span><span class="o">.</span><span class="n">describe</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[8]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>mean radius</th>
      <th>mean texture</th>
      <th>mean perimeter</th>
      <th>mean area</th>
      <th>mean smoothness</th>
      <th>mean compactness</th>
      <th>mean concavity</th>
      <th>mean concave points</th>
      <th>mean symmetry</th>
      <th>mean fractal dimension</th>
      <th>...</th>
      <th>worst texture</th>
      <th>worst perimeter</th>
      <th>worst area</th>
      <th>worst smoothness</th>
      <th>worst compactness</th>
      <th>worst concavity</th>
      <th>worst concave points</th>
      <th>worst symmetry</th>
      <th>worst fractal dimension</th>
      <th>target</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>569.000000</td>
      <td>569.000000</td>
      <td>569.000000</td>
      <td>569.000000</td>
      <td>569.000000</td>
      <td>569.000000</td>
      <td>569.000000</td>
      <td>569.000000</td>
      <td>569.000000</td>
      <td>569.000000</td>
      <td>...</td>
      <td>569.000000</td>
      <td>569.000000</td>
      <td>569.000000</td>
      <td>569.000000</td>
      <td>569.000000</td>
      <td>569.000000</td>
      <td>569.000000</td>
      <td>569.000000</td>
      <td>569.000000</td>
      <td>569.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>14.127292</td>
      <td>19.289649</td>
      <td>91.969033</td>
      <td>654.889104</td>
      <td>0.096360</td>
      <td>0.104341</td>
      <td>0.088799</td>
      <td>0.048919</td>
      <td>0.181162</td>
      <td>0.062798</td>
      <td>...</td>
      <td>25.677223</td>
      <td>107.261213</td>
      <td>880.583128</td>
      <td>0.132369</td>
      <td>0.254265</td>
      <td>0.272188</td>
      <td>0.114606</td>
      <td>0.290076</td>
      <td>0.083946</td>
      <td>0.627417</td>
    </tr>
    <tr>
      <th>std</th>
      <td>3.524049</td>
      <td>4.301036</td>
      <td>24.298981</td>
      <td>351.914129</td>
      <td>0.014064</td>
      <td>0.052813</td>
      <td>0.079720</td>
      <td>0.038803</td>
      <td>0.027414</td>
      <td>0.007060</td>
      <td>...</td>
      <td>6.146258</td>
      <td>33.602542</td>
      <td>569.356993</td>
      <td>0.022832</td>
      <td>0.157336</td>
      <td>0.208624</td>
      <td>0.065732</td>
      <td>0.061867</td>
      <td>0.018061</td>
      <td>0.483918</td>
    </tr>
    <tr>
      <th>min</th>
      <td>6.981000</td>
      <td>9.710000</td>
      <td>43.790000</td>
      <td>143.500000</td>
      <td>0.052630</td>
      <td>0.019380</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.106000</td>
      <td>0.049960</td>
      <td>...</td>
      <td>12.020000</td>
      <td>50.410000</td>
      <td>185.200000</td>
      <td>0.071170</td>
      <td>0.027290</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.156500</td>
      <td>0.055040</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>11.700000</td>
      <td>16.170000</td>
      <td>75.170000</td>
      <td>420.300000</td>
      <td>0.086370</td>
      <td>0.064920</td>
      <td>0.029560</td>
      <td>0.020310</td>
      <td>0.161900</td>
      <td>0.057700</td>
      <td>...</td>
      <td>21.080000</td>
      <td>84.110000</td>
      <td>515.300000</td>
      <td>0.116600</td>
      <td>0.147200</td>
      <td>0.114500</td>
      <td>0.064930</td>
      <td>0.250400</td>
      <td>0.071460</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>13.370000</td>
      <td>18.840000</td>
      <td>86.240000</td>
      <td>551.100000</td>
      <td>0.095870</td>
      <td>0.092630</td>
      <td>0.061540</td>
      <td>0.033500</td>
      <td>0.179200</td>
      <td>0.061540</td>
      <td>...</td>
      <td>25.410000</td>
      <td>97.660000</td>
      <td>686.500000</td>
      <td>0.131300</td>
      <td>0.211900</td>
      <td>0.226700</td>
      <td>0.099930</td>
      <td>0.282200</td>
      <td>0.080040</td>
      <td>1.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>15.780000</td>
      <td>21.800000</td>
      <td>104.100000</td>
      <td>782.700000</td>
      <td>0.105300</td>
      <td>0.130400</td>
      <td>0.130700</td>
      <td>0.074000</td>
      <td>0.195700</td>
      <td>0.066120</td>
      <td>...</td>
      <td>29.720000</td>
      <td>125.400000</td>
      <td>1084.000000</td>
      <td>0.146000</td>
      <td>0.339100</td>
      <td>0.382900</td>
      <td>0.161400</td>
      <td>0.317900</td>
      <td>0.092080</td>
      <td>1.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>28.110000</td>
      <td>39.280000</td>
      <td>188.500000</td>
      <td>2501.000000</td>
      <td>0.163400</td>
      <td>0.345400</td>
      <td>0.426800</td>
      <td>0.201200</td>
      <td>0.304000</td>
      <td>0.097440</td>
      <td>...</td>
      <td>49.540000</td>
      <td>251.200000</td>
      <td>4254.000000</td>
      <td>0.222600</td>
      <td>1.058000</td>
      <td>1.252000</td>
      <td>0.291000</td>
      <td>0.663800</td>
      <td>0.207500</td>
      <td>1.000000</td>
    </tr>
  </tbody>
</table>
<p>8 rows × 31 columns</p>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [9]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Check for missing values</span>
<span class="n">df_cancer</span><span class="o">.</span><span class="n">isnull</span><span class="p">()</span><span class="o">.</span><span class="n">mean</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[9]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>mean radius                0.0
mean texture               0.0
mean perimeter             0.0
mean area                  0.0
mean smoothness            0.0
mean compactness           0.0
mean concavity             0.0
mean concave points        0.0
mean symmetry              0.0
mean fractal dimension     0.0
radius error               0.0
texture error              0.0
perimeter error            0.0
area error                 0.0
smoothness error           0.0
compactness error          0.0
concavity error            0.0
concave points error       0.0
symmetry error             0.0
fractal dimension error    0.0
worst radius               0.0
worst texture              0.0
worst perimeter            0.0
worst area                 0.0
worst smoothness           0.0
worst compactness          0.0
worst concavity            0.0
worst concave points       0.0
worst symmetry             0.0
worst fractal dimension    0.0
target                     0.0
dtype: float64</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Data-visualization">Data visualization<a class="anchor-link" href="#Data-visualization">¶</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [10]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Visualize the dataset</span>
<span class="n">sns</span><span class="o">.</span><span class="n">pairplot</span><span class="p">(</span><span class="n">df_cancer</span><span class="p">,</span> <span class="n">hue</span> <span class="o">=</span> <span class="s1">'target'</span><span class="p">,</span> <span class="nb">vars</span> <span class="o">=</span> <span class="p">[</span><span class="s1">'mean radius'</span><span class="p">,</span> <span class="s1">'mean texture'</span><span class="p">,</span> <span class="s1">'mean area'</span><span class="p">,</span> <span class="s1">'mean perimeter'</span><span class="p">,</span> <span class="s1">'mean smoothness'</span><span class="p">]</span> <span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[10]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>&lt;seaborn.axisgrid.PairGrid at 0x1e259a3b310&gt;</pre>
</div>

</div>

<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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IpFIJBJJHWSgLJFIJBKJRCKRSCQSSR1koCyRSCQSiUQikUgkEkkdZKAskUgkEolEIpFIJBJJHWSgLGl11q5dy/Tp0wF47rnn+Mc//hFliSQdneXLl7Ns2bIWH//555/z3HPPtaJEEolEcmby1ltv8dJLL7Xa+ebNm8e3337baueTSJrCrl27eOSRRwDYunWrUb5McmYh6yhLTit33XVXtEWQnAHs2LGDHj16tPj43bt3U15e3ooSSSQSyZnJ9ddf36rn27x5M5MnT27Vc0okjfHjjz9SUFAQbTEkUUYGyjHI1q1b+dOf/kRubi4HDx4kPj6eW2+9lddff52DBw8yfPhwHnzwQQA+++wzXnzxRbxeLzabjTlz5nDJJZdQXFzMI488QklJCUVFReTl5fHss8+SkZHBkCFDGD9+PFu2bOHEiRNce+213H333SFyDBkyhN69e/P9999z7733Yjab+etf/4rH46G0tJRx48YZxz333HOsWbOG1NRUunbtapxj7ty59OjRg9/+9rdccMEFbNmyhfT0dADjb6vVygMPPMBPP/2Eqqr06tWL+fPno6pywUOsEwu6un79ej777DM2bdqEzWbjhhtu4MUXX2TdunXouk5eXh6PPvooKSkpTJw4kalTp3LDDTewfPlyXnvtNR5++GHefvttNE0jKSmJrl278vHHH/PXv/4VgPfee8/4e+7cuTgcDo4cOcKvfvUr7rrrLhYtWsS2bdvQNI2f/exnzJs3j8TExDa/F5JTIxZ0GWDDhg1h7ezWrVtZsGABdrud6upqVq5cyZdfftlsOSSxSazo35AhQxg9ejSbNm2isrKSm2++malTpzZ43eeff55vvvmGwsJCLrjgArp27UpZWRmPPPIIQ4YMYcyYMXz11VeUl5czc+ZMvv76a/79739jNpt58cUXyc7OpqCggPnz53PixAm8Xi+jR4/m97//PYsXL6awsJD77ruPhQsX0r17dxYsWMAPP/yA1+vlyiuvZPbs2ZjNZn7+859z9dVXs3fvXhYtWsRFF13UpvewIxIrevnmm2/y9ttvY7FYsFqtzJ8/n/POO6/J+rVv3z7mz5+Pw+FAURRuueUWxo0bB8A777zD66+/jqqqdOrUiYcffhibzcaSJUuorKzkgQceYNy4cTidTu655x4OHDiA2+3miSeeoG/fvsydO5fExES+//57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%0A">
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [11]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Check correlation in the features by using heatmap</span>
<span class="kn">from</span> <span class="nn">heatmap</span> <span class="kn">import</span> <span class="n">corrplot</span>
<span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">(</span><span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">8</span><span class="p">,</span> <span class="mi">8</span><span class="p">))</span>
<span class="n">corrplot</span><span class="p">(</span><span class="n">df_cancer</span><span class="o">.</span><span class="n">corr</span><span class="p">(),</span> <span class="n">size_scale</span><span class="o">=</span><span class="mi">300</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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MuPHj+edd97hzz//5Ny5c1y4cIHHH3+cl19+GYPBQEREBEeOHMFgMDBmzBieeeYZLl26xMyZM8nNzUWj0RAaGkq/fv1YunQpBw4cQKPR8MADDzB16lTLnlTKvrMXEY4FAFTmxyFJ4o4nAMScIShLc3aubxQrXqmpqSxYsICEhARiY2Np164diYmJuLm5kZSURGZmJsuXL2fDhg1s27YNX19fli1bhtFoJC4ujqioKLZv386kSZOIjo4211tYWEh8fDwhISGsWrWqQrsrV67k/fffJzExkc6dO/P777/L0ufatWvMmzePNWvWsGPHDjw8PFi4cCEFBQX8+9//Zu7cuWzfvp2goCD+/e9/M2jQIAICApg+fbo5SXZBQQGbN29m3bp1vP3222adTp06xYYNG9i8eTPR0dFkZ2ezadMmALZu3cqWLVv46quvOHbsGFu2bGHo0KEkJiYyffp0UlJSuHDhAvv372f79u18+umnnD17lvz82u8wUUL5wdzSHCcFAoEyxJwhaEk0+IoXQPfu3enUqRMAjo6O+Pj4AODi4kJ2djapqalcvHiRiRMnAsVJou3t7dFoNKxZs4bk5GTS0tI4cuQImlK7vUqMnG7dupGVlVWhXX9/f5588kkeeOABhg8fjru7O4cPH65RnxMnTtCnTx9cXV0BGD9+PNHR0aSnp2NnZ0efPn0AGDFiBPPmzePGjRsV2h42bBiSJNGtWzf++uufcAXe3t5YWVnRvn17HBwcuHHjBt9//z2//PILhw4dAiA3N5dTp07h4+PDtGnT+OWXX/Dz82PChAlotVqsra0JCgrC39+fmTNnmhNzCwQCgUDQFNBIUq3De8hpoyFoFIaXXq8v81mrLev3YTAY8PDwICoqCoD8/HxycnLIyclh3LhxBAYG4unpiZubG7GxsWa5EoOjqqen0NBQfv31V7755htmzZrF1KlT6dixY436GMs5AppMJoqKiip8X/JbZUmqS+osr1tpI6kk+7vBYGDWrFk8+OCDAGRmZtK6dWusra1JSkpi37597Nq1i61btxITE8PmzZs5cuQI+/fvJygoiI0bN3LnnXdW2gf1QUnm+tKfBQKBQCCQjQVeNVbq/mABGsWrxpro27cvx48fJy0tDYC1a9cSERFBeno6kiQxefJkvL292bNnT6VGTmUUFRXx4IMP4ujoyEsvvcTo0aP5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4TwEtRNLhuyaY9IIrE2+QUH5NR8DdRWO7xXmNHC8hvK4VqCrMrSG1LBAtsCg12OQOXNuMQox41WjqMroAvjf//7HuXPn7KSNc1BbBymBQGBL5ETqE1SHqlrWeVq9JMipjWU4AJsYXgaDgQULFvDtt9+iUql4+eWXefXVVzlz5gzTp08nLy+POnXqEBUVha+vL1OnTsXDw4NffvmFy5cv8+abbzJs2DDy8vKIiori9OnTuLi4MHXqVLp168Z//vMfNmzYwL1799BoNCxcuJAzZ86wbt064uLiAEhMTCQnJ4fIyEjmz5/Pvn370Ol0DB06lNdee81E37179/Lpp5+iVqs5f/48vr6+fPDBB7i4uJCcnMzKlStRKBS0b9+eadOmUbduXVq3bs3x48dZunQply9fJicnhwsXLjB8+HDeeOMNZs+ezfnz55kxYwavv/46kyZN4u7duyiVSqKjo8tFlz906BBz5syhoKAAT09PZsyYQYsWLQgLC6NBgwacPHmSRYsWMWrUKJ5++mmuXr3K+vXrWbFiBenp6ahUKnr06MHkyZO5ePEio0ePxtPTEzc3N2NybYFAIBAIBI7FJimDtmzZwoEDB9i4cSPr1q0jJSWFq1evMnnyZMLCwti4cSORkZG8/fbb3L9f7Mh96dIlvvjiCz777DPmz58PwOLFi/nDH/7A119/zfz581m0aBF37tzh22+/JTExka+++orAwEBWr15N7969OXLkCDdv3gRg06ZNDBo0iLVr1wKQmprK+vXr+e677/jxxx/L6Xzw4EGioqLYsmULhYWFrF69muPHjxMXF0diYiIbN27E3d2dTz75pFzd48ePs2LFCtatW0d8fDy3bt0iOjqap59+mvfff5/169cTGBhISkoK48eP56effjKpf//+faKjo1m4cCGpqamMGjWKadOmGT9v3bo1W7dupW3btty4cYMxY8awYcMGdu3aRUZGBsnJyaSmppKTk0NSUhIAZ86cITY2VhhdAoFAIKhxGAwGuxyOwCYzXvv376d///64uLjg4uJizEH422+/8Ze/FEdSfuaZZ2jQoAGnT58GoEePHigUCv74xz+Sl5dnvM6CBQuAYuNjzZo1ACxcuJBNmzZx9uxZduzYQdu2bdFoNDz//PNs27aNHj16kJeXh6+vL8uXLyc7O5s9e/YAcPfuXY4fP86f//xnE507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fChJkiRduXJFWrFihbRu3TrJx8dHunr1qrRmzRppypQpkl6vl65fv17AtpCQEOn333+XgoODJUmSpPT0dOntt9+WcnJypK1bt0rTp0+XEhMT88n8+uuv0uDBg6VffvlFOn/+vPH3H3/8UVq0aJH02muvSXFxcflkoqKipL59+0rh4eHS7t27pVu3bklXrlyRduzYIc2YMUPq06ePtGfPHkmSJCkzM1P697//LV2+fFm6ffu2NHbsWKlHjx5SQECA8XwPHjyQjhw5In300UfS+vXr/5+9N4/LeXv7R9+JtkpIkSiUSIYMmcnYqElESZpkGzPENmzCVpuMobDZNKBBpB0laZ5TadScSoPmuTR3nT967vV0q+9zzu93znPO6/ke77+479a9xs9a1+da7+t9DRrDhIQEcnBwoLNnz9K7d++opaWFPn78SOrq6qSrq0tBQUFERFRXV0cODg5cfZOVleXqF+d3X79+TRoaGtTc3My+c3Fxob1795K5uTk9evSIIiIi6NGjR/Trr79SYWEhERF1dXUNah8R0cOHD9m4ExGFhITQ2rVrqbKykpKTk6mmpoarTGdnJx06dIjS09PZZ6dPn6b9+/cTEdH9+/epqqqKfsS3b99IU1OTEhISiIgoICCA9PX1KSUlhWJiYujw4cNUXl7OVebz58+kq6tLra2trMzFixcpNjaWYmNj6cqVK1RbWzuoX5WVlbR9+3YqKytjv3Pp0iXy8vKioqIievToEVVWVnKV46w1FxcX9jtdXV20bt06iomJobKyMkpLSxvUrzNnzpCXlxf7v4ODA+3bt4/a29vJw8ODcnNzB7UvIiKCfvvtN672njhxgvz9/YmIqLi4mH3HKdfV1UXR0dF0584d9l1rayutX7+e/P39qbKycsi6enp66MyZM1xrKTQ0lExMTIio/zn/8Tmpr68nIqLa2lo6dOgQ2djYUGlpKb148YKOHj1KOjo6Q9b15s0b2rx5M0VHRxNR/55hbW1NFhYW5OjoSMrKylRQUMBVpqKigvT09Ojbt2/k6+tLW7dupeLiYqqpqaGMjAwyMDAYtC6IiF6+fEm3b98mBwcHNl5qamr05csXio2NpT179lBdXR1XGWdnZzIyMqJ79+5x9TkwMJCOHTtG2trabC/k4PPnz6StrU3l5eUUHR1NFRUVlJ2dTT4+PmRsbExaWloUHBzM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%0A">
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [12]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Analyze the independent variables</span>
<span class="n">fig</span><span class="p">,</span> <span class="p">(</span><span class="n">ax1</span><span class="p">,</span> <span class="n">ax2</span><span class="p">)</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">subplots</span><span class="p">(</span><span class="mi">1</span><span class="p">,</span> <span class="mi">2</span><span class="p">,</span> <span class="n">figsize</span> <span class="o">=</span> <span class="p">(</span><span class="mi">20</span><span class="p">,</span> <span class="mi">6</span><span class="p">))</span>

<span class="n">sns</span><span class="o">.</span><span class="n">countplot</span><span class="p">(</span><span class="n">df_cancer</span><span class="p">[</span><span class="s1">'target'</span><span class="p">],</span> <span class="n">label</span> <span class="o">=</span> <span class="s2">"Count"</span><span class="p">,</span> <span class="n">ax</span> <span class="o">=</span> <span class="n">ax1</span><span class="p">)</span> 
<span class="n">ax1</span><span class="o">.</span><span class="n">set_xlabel</span><span class="p">(</span><span class="s2">"Target"</span><span class="p">);</span>
<span class="n">ax1</span><span class="o">.</span><span class="n">set_ylabel</span><span class="p">(</span><span class="s2">"Count"</span><span class="p">);</span>

<span class="n">sns</span><span class="o">.</span><span class="n">scatterplot</span><span class="p">(</span><span class="n">x</span> <span class="o">=</span> <span class="s1">'mean area'</span><span class="p">,</span> <span class="n">y</span> <span class="o">=</span> <span class="s1">'mean smoothness'</span><span class="p">,</span> <span class="n">hue</span> <span class="o">=</span> <span class="s1">'target'</span><span class="p">,</span> <span class="n">alpha</span><span class="o">=</span> <span class="mf">0.5</span><span class="p">,</span> <span class="n">data</span> <span class="o">=</span> <span class="n">df_cancer</span><span class="p">,</span> <span class="n">ax</span> <span class="o">=</span> <span class="n">ax2</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[12]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>&lt;matplotlib.axes._subplots.AxesSubplot at 0x1e25be63fa0&gt;</pre>
</div>

</div>

<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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/e9/H8dxuO6667jmmmsOu92qVatYtmwZV155JQDNzc3cddddNDc3E4lEeOihh2hsbDzsviIiIlI8SkvL+OY3HwHAti0cxzvhcyjoLS6CwSAPP/wwl156Keeeey6O47Bs2TLuv/9+nn76adavX8/PfvYzmpubSSaTA/slk0mampoKOTURERGRSaGpqYlvfetbPPnkkzz77LM89dRTbN++fcg2N910Ey+88MKg8VWrVnHhhRfy7LPP8slPfpKHHnroRE5dREREJrCCNym65ZZbuOGGG7jpppt45ZVX+O53vzvw3Oc+9zmeffZZ5s6dizGHmiP6vj/o8XBUVcXHbM4iIiIyMslkYrynMGWtW7eOZcuWUV5eDsDFF1/M2rVrufnmmwe2WbNmDR/96EcHtgFob29ny5Yt/OAHPwDgU5/6FOeee+6JnbyIiIhMWAULlHbs2EEul+Okk04iGo2yYsUKfvGLX1BeXs7FF18M9AdHtm1TV1dHS8uh27m2trYO6bF0LG1tvXie1saLyNjRBbLI8LW09BTstS3L6A9HR/HBSu+amho2btw4aJvrr++/Y+WGDRsGxvbs2UNDQwMPPvgg69evJ5lM8vWvf/3ETFpEREQmvIIFSnv37uXhhx/mJz/5CQAvvvgiZ599Nvfffz/Lli0jFovx1FNPccUVVzBt2jTC4TAbNmzgzDPP5LnnnuOCCy4o1NREREREJg3P846r0ttxHDZv3syXv/xl7rjjDv7t3/6Nr33ta/zoRz8a0fEV9p14+oPH+NM5KA46D8VhIp+H5mYL2y5oJ6ATZizeh2VZIzqfBQuUli9fzsaNG7n88ssJBAKsWLGCm2++mYqKCj772c/iOA4rVqzgsssuA+Chhx7irrvuore3l8WLF3PttdcWamoiIiIik0ZdXR3r1x+6jXBLS8uwKr2TySQlJSVceOGFAFx22WXcd999Iz6+qsRPrGQyUdCKQDk2nYPioPNQHCb6efA8b1yaWY+1sWrK7XneoPN5rCrxgvZQ+vKXv8yXv/zlQWPXXHPNYe88smjRIn72s58VcjoiIiIik855553HI488Qnt7O9FolF/+8pfce++9x9xvxowZ1NXV8etf/5rly5fzX//1XyxevPgEzFhEREQO55e/XMvjj/8zjuPw6U9/lk996i8GPb9t21YefPA+UqkUS5eezle/ege2XfDW2Ec0OWq7RERERKao2tpabrvtNq699louv/xyLrvsMk499VRuuOEGXn/99aPu+8gjj/DYY49x2WWX8fjjj3P//fefoFmLiIjI+7W0NPPoo9/je997jB/84El+/vP/4J133h60zTe+8XVuu20VP/3pM/i+z5o1z47TbPuNX5QlIiIiImNi5cqVrFy5ctDYo48+OmS7Bx98cNDjOXPmjLhnkoiIyFT2yhsHeebXO2jrzlJVGubK5XM5d3HdqF93/fpXOeOMsygtLQPgwgs/yksvvcjs2XMAOHjwANlsllNOWQLAJZes5J//+f9wxRVXjfrYx0sVSiIiIiIiIiIix/DKGwf51+e30NadBaCtO8u/Pr+FV944OOrXbm1toaqqeuBxVVU1zc3Nw35+PChQEhERERERERE5hmd+vYPcB5pf5xyPZ369Y9Svfbi7tlqWGfbz40GBkoiIiIiIiIjIMbxXmTTc8ZGoqamlra114HF7exvV1clhPz8eFCiJiIiIiIiIiBxDVWl4ROMjcdZZ57Bhw+/p6Oggk8nw0kv/Lx/60LkDz9fV1RMKhdi48TUA1q79BcuWnTfq446GAiURERERERERkWO4cvlcQvbgGCVkW1y5fO6oXzuZrOGGG77ELbfcyOc/fzUXXXQxJ598Cl/96i1s2bIZgLvvvo9HHvkmV1/9KdLpPq666jOjPu5o6C5vIiIiIiIiIiLH8N7d3ApxlzeAFSs+zooVHx809tBDDw98PX/+Ah599PExOdZYUKAkIiIiIiIiIjIM5y6uG7MAaaLTkjcRERERERERERkRBUoiIiIiIiIiIjIiCpRERERERERERGREFCiJiIiIiIiIiMiIKFASEREREREREZERUaAkIiIiIiIiIlIEUqlePve5v+DAgf1Dntu2bStf/OLn+MxnruTBB+/FcZxxmOEhCpRERERERERERMbZG29s4ktfup49e3Yf9vlvfOPr3HbbKn7602fwfZ81a549wTMcTIGSiIiIiIiIiMgw5Lato/fJr9Dzf3+e3ie/Qm7bujF77TVr/oO//dv/SXV1cshzBw8eIJvNcsopSwC45JKV/Nd//T9jduzjYY/r0UVEREREREREJoDctnVkf/NDcHIA+L1t/Y+B0PzzRv36X/va14/4XGtrC1VV1QOPq6qqaW5uHvUxR0MVSiIiIiIiIiIix5D7/b8PhEkDnFz/eIF5nocxZuCx7/tYljnKHoWnQElERERERERE5Bj83rYRjY+lmppa2tpaBx63t7cddmnciaRASURERERERETkGEy8akTjY6murp5QKMTGja8BsHbtL1i2bPTL7EZDgZKIiIiIiIiIyDGEzv4U2KHBg3aof7xAvvrVW9iyZTMAd999H4888k2uvvpTpNN9XHXVZwp23OFQU24RERERERERkWN4r/F27vf/jt/bholXETr7U2PSkPv9fvazNQNfP/TQwwNfz5+/gEcffXxMjzUaCpRERERERERERIYhNP+8MQ+QJioteRMRERERERERkRFRoCQiIiIiIiIiIiOiQElEREREREREpiTf98d7CkXB9z3AjGgfBUoiIiIiIiIiMuXYdohUqntKh0q+7+M4eTo7WwmFIiPaV025RURERERERGTKqahI0tHRQm9v53hPZVQsy8LzvFHsHyAajROPl41oPwVKIiIiIiIiIjLlBAI21dX14z2NUUsmE7S09Jzw42rJm4iIiIiIiIiIjIgCJRERERERERERGREFSiIiIiIiIiIiMiIKlEREREREREREZEQKGih9+9vf5pJLLuHSSy/lBz/4AQDr1q1j5cqVrFixgm9961sD27755ptceeWVXHzxxdx55504jlPIqYmIiIiIiIiMq0DAEAgYjBnvmYiMXMECpVdffZXf/e53/PznP+ff//3f+dGPfsSWLVtYvXo13/ve9/jFL37Bpk2b+PWvfw3A7bffzt13380LL7yA7/s8/fTThZqaiIiIiIiIyLgxBnoyDuu3tvDr1/azq6kX1/fHe1oiI1KwQOmcc87h8ccfx7Zt2tracF2X7u5uZs6cyfTp07Ftm5UrV7J27Vr27dtHJpNh6dKlAFx55ZWsXbu2UFMTERERERERGTd9OZeX/7SPXQe6ae1M84etzby1p0uVSjKhFHTJWzAY5OGHH+bSSy/l3HPPpbm5mWQyOfB8TU0NTU1NQ8aTySRNTU2FnJqIiIiIiIjIuGjrzpDNuYPGdh/sJut44zQjkZGzC32AW265hRtuuIGbbrqJnTt3Yt4Xufq+jzEGz/MOOz4SVVXxMZuziIiIjEwymRjvKYiIiEwYh73aVXWSTDAFC5R27NhBLpfjpJNOIhqNsmLFCtauXUsgEBjYpqWlhZqaGurq6mhpaRkYb21tpaamZkTH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%0A">
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Data-pre-processing">Data pre-processing<a class="anchor-link" href="#Data-pre-processing">¶</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [13]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Define the indepedent and dependent variables</span>
<span class="n">x</span> <span class="o">=</span> <span class="n">df_cancer</span><span class="o">.</span><span class="n">drop</span><span class="p">([</span><span class="s1">'target'</span><span class="p">],</span> <span class="n">axis</span> <span class="o">=</span> <span class="mi">1</span><span class="p">)</span>
<span class="n">y</span> <span class="o">=</span> <span class="n">df_cancer</span><span class="p">[</span><span class="s1">'target'</span><span class="p">]</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [14]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Split the dataset</span>
<span class="kn">from</span> <span class="nn">sklearn.model_selection</span> <span class="kn">import</span> <span class="n">train_test_split</span>
<span class="n">x_train</span><span class="p">,</span> <span class="n">x_test</span><span class="p">,</span> <span class="n">y_train</span><span class="p">,</span> <span class="n">y_test</span> <span class="o">=</span> <span class="n">train_test_split</span><span class="p">(</span><span class="n">x</span><span class="p">,</span> <span class="n">y</span><span class="p">,</span> <span class="n">test_size</span> <span class="o">=</span> <span class="mf">0.20</span><span class="p">,</span> <span class="n">random_state</span> <span class="o">=</span> <span class="mi">0</span><span class="p">)</span>
<span class="n">x_train</span><span class="o">.</span><span class="n">shape</span><span class="p">,</span> <span class="n">y_train</span><span class="o">.</span><span class="n">shape</span><span class="p">,</span> <span class="n">x_test</span><span class="o">.</span><span class="n">shape</span><span class="p">,</span> <span class="n">y_test</span><span class="o">.</span><span class="n">shape</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[14]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>((455, 30), (455,), (114, 30), (114,))</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [15]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Scale the features</span>
<span class="kn">from</span> <span class="nn">sklearn.preprocessing</span> <span class="kn">import</span> <span class="n">StandardScaler</span>
<span class="n">scaler</span> <span class="o">=</span> <span class="n">StandardScaler</span><span class="p">()</span>
<span class="n">scaler</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">x_train</span><span class="p">)</span>
<span class="n">X_train</span> <span class="o">=</span> <span class="n">scaler</span><span class="o">.</span><span class="n">transform</span><span class="p">(</span><span class="n">x_train</span><span class="p">)</span>
<span class="n">X_test</span> <span class="o">=</span> <span class="n">scaler</span><span class="o">.</span><span class="n">transform</span><span class="p">(</span><span class="n">x_test</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Model-creation">Model creation<a class="anchor-link" href="#Model-creation">¶</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [16]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Create Machine Learning models</span>
<span class="k">def</span> <span class="nf">models</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">):</span>
    
    <span class="c1"># Use Logistic Regression</span>
    <span class="kn">from</span> <span class="nn">sklearn.linear_model</span> <span class="kn">import</span> <span class="n">LogisticRegression</span>
    <span class="n">log</span> <span class="o">=</span> <span class="n">LogisticRegression</span><span class="p">(</span><span class="n">random_state</span> <span class="o">=</span> <span class="mi">0</span><span class="p">)</span>
    <span class="n">log</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">)</span>
    
    <span class="c1"># use KNeighbors</span>
    <span class="kn">from</span> <span class="nn">sklearn.neighbors</span> <span class="kn">import</span> <span class="n">KNeighborsClassifier</span>
    <span class="n">knn</span> <span class="o">=</span> <span class="n">KNeighborsClassifier</span><span class="p">(</span><span class="n">n_neighbors</span> <span class="o">=</span> <span class="mi">5</span><span class="p">,</span> <span class="n">metric</span> <span class="o">=</span> <span class="s1">'minkowski'</span><span class="p">,</span> <span class="n">p</span> <span class="o">=</span> <span class="mi">2</span><span class="p">)</span>
    <span class="n">knn</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">)</span>
    
    <span class="c1"># Use SVM (Linear Kernel)</span>
    <span class="kn">from</span> <span class="nn">sklearn.svm</span> <span class="kn">import</span> <span class="n">SVC</span>
    <span class="n">svc_lin</span> <span class="o">=</span> <span class="n">SVC</span><span class="p">(</span><span class="n">kernel</span> <span class="o">=</span> <span class="s1">'linear'</span><span class="p">,</span> <span class="n">random_state</span> <span class="o">=</span> <span class="mi">0</span><span class="p">)</span>
    <span class="n">svc_lin</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">)</span>
    
    <span class="c1"># Use SVM (RBF Kernel)</span>
    <span class="kn">from</span> <span class="nn">sklearn.svm</span> <span class="kn">import</span> <span class="n">SVC</span>
    <span class="n">svc_rbf</span> <span class="o">=</span> <span class="n">SVC</span><span class="p">(</span><span class="n">kernel</span> <span class="o">=</span> <span class="s1">'rbf'</span><span class="p">,</span> <span class="n">random_state</span> <span class="o">=</span> <span class="mi">0</span><span class="p">)</span>
    <span class="n">svc_rbf</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">)</span>
    
    <span class="c1"># Use GaussianNB</span>
    <span class="kn">from</span> <span class="nn">sklearn.naive_bayes</span> <span class="kn">import</span> <span class="n">GaussianNB</span>
    <span class="n">gauss</span> <span class="o">=</span> <span class="n">GaussianNB</span><span class="p">()</span>
    <span class="n">gauss</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">)</span>
    
    <span class="c1"># Use Decision Tree</span>
    <span class="kn">from</span> <span class="nn">sklearn.tree</span> <span class="kn">import</span> <span class="n">DecisionTreeClassifier</span>
    <span class="n">tree</span> <span class="o">=</span> <span class="n">DecisionTreeClassifier</span><span class="p">(</span><span class="n">criterion</span> <span class="o">=</span> <span class="s1">'entropy'</span><span class="p">,</span> <span class="n">random_state</span> <span class="o">=</span> <span class="mi">0</span><span class="p">)</span>
    <span class="n">tree</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">)</span>
    
    <span class="c1"># Use RandomforestClassifier</span>
    <span class="kn">from</span> <span class="nn">sklearn.ensemble</span> <span class="kn">import</span> <span class="n">RandomForestClassifier</span>
    <span class="n">forest</span> <span class="o">=</span> <span class="n">RandomForestClassifier</span><span class="p">(</span><span class="n">criterion</span> <span class="o">=</span> <span class="s1">'entropy'</span><span class="p">,</span> <span class="n">random_state</span> <span class="o">=</span> <span class="mi">0</span><span class="p">)</span>
    <span class="n">forest</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">)</span>
    
    <span class="c1"># Use XGBoost Classifer</span>
    <span class="kn">from</span> <span class="nn">xgboost</span> <span class="kn">import</span> <span class="n">XGBClassifier</span>
    <span class="n">xgb</span> <span class="o">=</span> <span class="n">XGBClassifier</span><span class="p">()</span>
    <span class="n">xgb</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">)</span>
    
    <span class="c1"># Print the training accuracy for each model</span>
    <span class="nb">print</span><span class="p">(</span><span class="s1">'model[0] Logistic Regression Training Accuracy: '</span><span class="p">,</span> <span class="n">log</span><span class="o">.</span><span class="n">score</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">))</span>
    <span class="nb">print</span><span class="p">(</span><span class="s1">'model[1] KNNeighbors Training Accuracy: '</span><span class="p">,</span> <span class="n">knn</span><span class="o">.</span><span class="n">score</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">))</span>
    <span class="nb">print</span><span class="p">(</span><span class="s1">'model[2] SVC Linear Training Accuracy: '</span><span class="p">,</span> <span class="n">svc_lin</span><span class="o">.</span><span class="n">score</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">))</span>
    <span class="nb">print</span><span class="p">(</span><span class="s1">'model[3] SVC RBF Training Accuracy: '</span><span class="p">,</span> <span class="n">svc_rbf</span><span class="o">.</span><span class="n">score</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">))</span>
    <span class="nb">print</span><span class="p">(</span><span class="s1">'model[4] Gauss Training Accuracy: '</span><span class="p">,</span> <span class="n">gauss</span><span class="o">.</span><span class="n">score</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">))</span>
    <span class="nb">print</span><span class="p">(</span><span class="s1">'model[5] Decision Tree  Training Accuracy: '</span><span class="p">,</span> <span class="n">tree</span><span class="o">.</span><span class="n">score</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">))</span>
    <span class="nb">print</span><span class="p">(</span><span class="s1">'model[6] Random Forest Training Accuracy: '</span><span class="p">,</span> <span class="n">forest</span><span class="o">.</span><span class="n">score</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">))</span>
    <span class="nb">print</span><span class="p">(</span><span class="s1">'model[7] XGBoost Training Accuracy: '</span><span class="p">,</span> <span class="n">xgb</span><span class="o">.</span><span class="n">score</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">))</span>
    
    <span class="k">return</span> <span class="n">log</span><span class="p">,</span> <span class="n">knn</span><span class="p">,</span> <span class="n">svc_lin</span><span class="p">,</span> <span class="n">svc_rbf</span><span class="p">,</span> <span class="n">gauss</span><span class="p">,</span> <span class="n">tree</span><span class="p">,</span> <span class="n">forest</span><span class="p">,</span> <span class="n">xgb</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Model-evaluation">Model evaluation<a class="anchor-link" href="#Model-evaluation">¶</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [17]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Show Training accuracy score</span>
<span class="n">model</span> <span class="o">=</span> <span class="n">models</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>model[0] Logistic Regression Training Accuracy:  0.989010989010989
model[1] KNNeighbors Training Accuracy:  0.978021978021978
model[2] SVC Linear Training Accuracy:  0.989010989010989
model[3] SVC RBF Training Accuracy:  0.9846153846153847
model[4] Gauss Training Accuracy:  0.9472527472527472
model[5] Decision Tree  Training Accuracy:  1.0
model[6] Random Forest Training Accuracy:  1.0
model[7] XGBoost Training Accuracy:  1.0
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [18]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Show the confusion matrix and accuracy for all the models on the test data</span>
<span class="kn">from</span> <span class="nn">sklearn.metrics</span> <span class="kn">import</span> <span class="n">confusion_matrix</span>
<span class="kn">from</span> <span class="nn">sklearn.metrics</span> <span class="kn">import</span> <span class="n">accuracy_score</span>

<span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span> <span class="nb">len</span><span class="p">(</span><span class="n">model</span><span class="p">)</span> <span class="p">):</span>
    <span class="n">cm</span> <span class="o">=</span> <span class="n">confusion_matrix</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">model</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">predict</span><span class="p">((</span><span class="n">X_test</span><span class="p">)))</span>
    
    <span class="c1"># Extract TN, FP, FN, TP</span>
    <span class="n">TN</span><span class="p">,</span> <span class="n">FP</span><span class="p">,</span> <span class="n">FN</span><span class="p">,</span> <span class="n">TP</span> <span class="o">=</span> <span class="n">confusion_matrix</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">model</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">X_test</span><span class="p">))</span><span class="o">.</span><span class="n">ravel</span><span class="p">()</span>
    
    <span class="n">test_score</span> <span class="o">=</span> <span class="p">(</span><span class="n">TP</span> <span class="o">+</span> <span class="n">TN</span><span class="p">)</span> <span class="o">/</span> <span class="p">(</span><span class="n">TN</span> <span class="o">+</span> <span class="n">FP</span> <span class="o">+</span> <span class="n">FN</span> <span class="o">+</span> <span class="n">TP</span><span class="p">)</span>
    
    <span class="nb">print</span><span class="p">(</span><span class="s1">'model[</span><span class="si">{}</span><span class="s1">] Testing Accuracy: "</span><span class="si">{}</span><span class="s1">"'</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">i</span><span class="p">,</span> <span class="n">test_score</span><span class="p">))</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>model[0] Testing Accuracy: "0.9649122807017544"
model[1] Testing Accuracy: "0.956140350877193"
model[2] Testing Accuracy: "0.9824561403508771"
model[3] Testing Accuracy: "0.9824561403508771"
model[4] Testing Accuracy: "0.9035087719298246"
model[5] Testing Accuracy: "0.9298245614035088"
model[6] Testing Accuracy: "0.9736842105263158"
model[7] Testing Accuracy: "0.9824561403508771"
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [19]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Create confusion matrix function</span>
<span class="n">y_predict</span> <span class="o">=</span> <span class="n">model</span><span class="p">[</span><span class="mi">7</span><span class="p">]</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">X_test</span><span class="p">)</span>
<span class="n">cm</span> <span class="o">=</span> <span class="n">confusion_matrix</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">y_predict</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [20]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Show confusion matrix</span>
<span class="n">sns</span><span class="o">.</span><span class="n">heatmap</span><span class="p">(</span><span class="n">cm</span><span class="p">,</span> <span class="n">annot</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[20]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>&lt;matplotlib.axes._subplots.AxesSubplot at 0x1e25cda86a0&gt;</pre>
</div>

</div>

<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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%0A">
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [21]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Check f1, precision and recall score</span>
<span class="kn">from</span> <span class="nn">sklearn.metrics</span> <span class="kn">import</span> <span class="n">f1_score</span><span class="p">,</span> <span class="n">precision_score</span><span class="p">,</span> <span class="n">recall_score</span>
<span class="n">UsedFitter</span> <span class="o">=</span> <span class="n">model</span><span class="p">[</span><span class="mi">7</span><span class="p">]</span>

<span class="nb">print</span><span class="p">(</span><span class="s1">'Precision Score:'</span><span class="p">,</span> <span class="n">precision_score</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">UsedFitter</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">X_test</span><span class="p">)))</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">'Recall Score:'</span><span class="p">,</span> <span class="n">recall_score</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">UsedFitter</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">X_test</span><span class="p">)))</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">'f1_score:'</span><span class="p">,</span> <span class="n">f1_score</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">UsedFitter</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">X_test</span><span class="p">)))</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Precision Score: 0.9710144927536232
Recall Score: 1.0
f1_score: 0.9852941176470589
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [22]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Implement-Fold Cross Validation</span>
<span class="kn">from</span> <span class="nn">sklearn.model_selection</span> <span class="kn">import</span> <span class="n">cross_val_score</span>
<span class="n">accuracies</span> <span class="o">=</span> <span class="n">cross_val_score</span><span class="p">(</span><span class="n">estimator</span> <span class="o">=</span> <span class="n">UsedFitter</span><span class="p">,</span> <span class="n">X</span> <span class="o">=</span> <span class="n">X_train</span><span class="p">,</span> <span class="n">y</span> <span class="o">=</span> <span class="n">y_train</span><span class="p">,</span> <span class="n">cv</span> <span class="o">=</span> <span class="mi">10</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">'Mean Accuracy:'</span><span class="p">,</span> <span class="n">accuracies</span><span class="o">.</span><span class="n">mean</span><span class="p">())</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">'Standard Deviation:'</span><span class="p">,</span> <span class="n">accuracies</span><span class="o">.</span><span class="n">std</span><span class="p">())</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Mean Accuracy: 0.9604347826086956
Standard Deviation: 0.02757472519245102
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [23]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Get feature importance</span>
<span class="n">importances</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">({</span><span class="s1">'feature'</span><span class="p">:</span> <span class="n">x</span><span class="o">.</span><span class="n">columns</span><span class="p">,</span> <span class="s1">'importance'</span><span class="p">:</span> <span class="n">np</span><span class="o">.</span><span class="n">round</span><span class="p">(</span><span class="n">UsedFitter</span><span class="o">.</span><span class="n">feature_importances_</span><span class="p">,</span> <span class="mi">3</span><span class="p">)})</span>
<span class="n">importances</span> <span class="o">=</span> <span class="n">importances</span><span class="o">.</span><span class="n">sort_values</span><span class="p">(</span><span class="s1">'importance'</span><span class="p">,</span> <span class="n">ascending</span> <span class="o">=</span> <span class="kc">False</span><span class="p">)</span><span class="o">.</span><span class="n">set_index</span><span class="p">(</span><span class="s1">'feature'</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">importances</span><span class="o">.</span><span class="n">head</span><span class="p">(</span><span class="mi">10</span><span class="p">))</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>                      importance
feature                         
worst concave points       0.353
mean concave points        0.211
worst perimeter            0.077
mean radius                0.075
worst area                 0.056
mean area                  0.031
worst concavity            0.027
radius error               0.026
worst texture              0.018
mean symmetry              0.016
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In [24]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Visualize the importance</span>
<span class="n">importances</span><span class="o">.</span><span class="n">head</span><span class="p">(</span><span class="mi">10</span><span class="p">)</span><span class="o">.</span><span class="n">plot</span><span class="o">.</span><span class="n">bar</span><span class="p">()</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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%0A">
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Conlusion">Conlusion<a class="anchor-link" href="#Conlusion">¶</a></h1><p>The importance of certain features varies to different model but in this case we used XGboost method which attempts to accurately predict a target variable by combining the estimates of a set of simpler, weaker models. In this model, we could see that concave point has the highest influence whether a patient is malignant or benign.</p>
<p>Machine learning technique was able to classify tumors into malignant or benign with 96% accuracy. The technique can rapidly evaluate breast masses and classify them in an automated fashion. Early breast cancer can dramatically save lives especially in developing world. The technique can be further improved by combining computer vision/ML techniques to directly classify cancer using tissue images.</p>

</div>
</div>
</div>
    </div>
  </div>
</body>

 


</html>