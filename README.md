CKEditor_Plugin_CKGoogledoc
===========================

本專案的原始碼是從 Drupal 的 Extend：CkEditor Plugin: Google Doc embedded iframe 傳承而來。
該Extend網址為：http://drupal.org/project/ckeditor-googledoc

本來單純想從該Extend移植該Plugin到自己的網站上，
卻發現做出來的iFrame是無法使用的，所以個檢查與修正。

本人對該程式碼沒有做太大的變動，
僅因為Google文件的Viewer經過結構的改變，
導致該Extend做出來的iFrame會失校，
所以針對這部分去做個改正。

所動的程式碼部分為plugin/ckgoogledoc/plugin.js 檔案的onOk : function()

- var inplaceTag = '<iframe src="http://docs.google.com/viewer?url=' + encodeURIComponent(url) + '&embedded=true" width="' + parseInt(width) + '" height="' + parseInt(height) + '" style="border: none;">';

+ var id = url.substring(32)
+ var inplaceTag = '<iframe src="https://docs.google.com/file/d/' + encodeURIComponent(id) + '/preview" width="' + parseInt(width) + '" height="' + parseInt(height) + '" style="border: none;">';




