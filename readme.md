## Source code:

```js
import React, {useEffect} from "react";

export const useEffectAsync = (fn, deps) => {
	useEffect(() => {
		fn();
	}, deps);
};

export const useComponentWillMount = (fn) => {
	let ref = useRef(false);

	useEffect(() => {
		if (!ref.current) {
			fn();
			ref.current = true;
		}
	});
};

export const useComponentWillMount2 = (fn) => {
	useEffect(() => {
		fn();
		/* eslint-disable-next-line */
	}, []);
};
```
