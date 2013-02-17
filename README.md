convert-key
===========

Converting object key to what you want.

callback
-----------

	var converter = require('convert-key');

	var obj = {
		hello_world: {
			Upper_and_underscore: "a",
			camelCasing: true,
		}
	}
	convertor.any(obj, function (key) {
		var matches = /([A-Z])/.exec(key);
		for (var occ in matches[1]) {
			key.replace(matches[1][occ], '_' + matches[1][occ].toLowerCase());
		}
		
		return key.replace(/^_+/, '').replace(/_+$/, '');
	});
	
	// obj = {hello_world: {upper_and_underscore:"a", canel_casing: true} }
