# deep-stub

    function deepStubObject(path, value) {
	var result = {};
	var paths = path.split('.');

	var moving = result;
	for (var x in paths) {
		moving[paths[x]] = x == (paths.length - 1) ? value : {};
		moving = moving[paths[x]];
	}

	return result;
    }
