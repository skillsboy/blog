---
title: "Analog Clock Using ReactJS"
date: 2022-03-03T12:20:07Z
draft: false
---

Simple analog clock using React JS (React Hooks)

<a href="https://skillsboy.github.io/react-analog-clock/" target="_blank">Demo</a>

<a href="https://github.com/skillsboy/react-analog-clock" target="_blank">Source Code</a>


![Analog clock using react](/images/analog-clock-using-reactJS.gif#center)

### Create react app

This will create a folder called ``my-app`` and will start a developing server for this project.

```bash
npx create-react-app my-app
cd my-app
npm start
```

### Clean App.js

Open ``App.js`` and remove unnecessary code.

{{<pwd>}}App.js{{</pwd>}}

```
import './App.css';

function App() {
    return (
		<div className="App">
		    <header className="App-header">
            
                    </header>
		</div>
	);
}

export default App;
```

### Add React Hooks

{{<pwd>}}App.js{{</pwd>}}

<div style="position: relative;">
<span style="position: absolute;top: 92px;width: 100%;height: 90px;background-color: rgb(0 255 0 / 30%);z-index: 1;pointer-events: none;"></span>

```
import { useEffect, useRef, useState } from 'react';
import './App.css';

function App() {
	const hourHand = useRef();
	const minHand = useRef();
	const secHand = useRef();
	const [timestamp, setTimestamp] = useState("");

	return (
		<div className="App">
			<header className="App-header">
				
			</header>
		</div>
	);
}

export default App;
```

</div>

### Add Clock Function

This function will calculate the angle of each clock hand and assign them.

{{<pwd>}}App.js{{</pwd>}}

<div style="position: relative;">
<span style="position: absolute;top: 197px;width: 100%;height: 320px;background-color: rgb(0 255 0 / 30%);z-index: 1;pointer-events: none;"></span>

```
import { useEffect, useRef, useState } from 'react';
import './App.css';

function App() {
	const hourHand = useRef();
	const minHand = useRef();
	const secHand = useRef();
	const [timestamp, setTimestamp] = useState("");

	function runClock() {
		const d = new Date(); //object of date()
		const hr = d.getHours();
		const min = d.getMinutes();
		const sec = d.getSeconds();
		const hr_rotation = 30 * hr + min / 2; //converting current time
		const min_rotation = 6 * min;
		const sec_rotation = 6 * sec;

		setTimestamp(d);

		hourHand.current.style.transform = `rotate(${hr_rotation}deg)`;
		minHand.current.style.transform = `rotate(${min_rotation}deg)`;
		secHand.current.style.transform = `rotate(${sec_rotation}deg)`;
	}

	return (
		<div className="App">
			<header className="App-header">
				
			</header>
		</div>
	);
}

export default App;
```

</div>

### Run at first render

Use `useEffect` to run the Clock Function in the first render and every next few miliseconds, so it updates the clock hands.

{{<pwd>}}App.js{{</pwd>}}

<div style="position: relative;">
<span style="position: absolute;top: 527px;width: 100%;height: 100px;background-color: rgb(0 255 0 / 30%);z-index: 1;pointer-events: none;"></span>

```
import { useEffect, useRef, useState } from 'react';
import './App.css';

function App() {
	const hourHand = useRef();
	const minHand = useRef();
	const secHand = useRef();
	const [timestamp, setTimestamp] = useState("");

	function runClock() {
		const d = new Date(); //object of date()
		const hr = d.getHours();
		const min = d.getMinutes();
		const sec = d.getSeconds();
		const hr_rotation = 30 * hr + min / 2; //converting current time
		const min_rotation = 6 * min;
		const sec_rotation = 6 * sec;

		setTimestamp(d);

		hourHand.current.style.transform = `rotate(${hr_rotation}deg)`;
		minHand.current.style.transform = `rotate(${min_rotation}deg)`;
		secHand.current.style.transform = `rotate(${sec_rotation}deg)`;
	}

	useEffect(() => {
		runClock();
		setInterval(runClock, 300);
	}, []);

	return (
		<div className="App">
			<header className="App-header">
				
			</header>
		</div>
	);
}

export default App;
```

</div>

### Add JSX (structure)

{{<pwd>}}App.js{{</pwd>}}

<div style="position: relative;">
<span style="position: absolute;top: 707px;width: 100%;height: 123px;background-color: rgb(0 255 0 / 30%);z-index: 1;pointer-events: none;"></span>

```
import { useEffect, useRef, useState } from 'react';
import './App.css';

function App() {
	const hourHand = useRef();
	const minHand = useRef();
	const secHand = useRef();
	const [timestamp, setTimestamp] = useState("");

	function runClock() {
		const d = new Date(); //object of date()
		const hr = d.getHours();
		const min = d.getMinutes();
		const sec = d.getSeconds();
		const hr_rotation = 30 * hr + min / 2; //converting current time
		const min_rotation = 6 * min;
		const sec_rotation = 6 * sec;

		setTimestamp(d);

		hourHand.current.style.transform = `rotate(${hr_rotation}deg)`;
		minHand.current.style.transform = `rotate(${min_rotation}deg)`;
		secHand.current.style.transform = `rotate(${sec_rotation}deg)`;
	}

	useEffect(() => {
		runClock();
		setInterval(runClock, 300);
	}, []);

	return (
		<div className="App">
			<header className="App-header">
				<div className="clock">
					<span ref={hourHand} className="hour"></span>
					<span ref={minHand} className="min"></span>
					<span ref={secHand} className="sec"></span>
				</div>
				<p><code>{timestamp.toString()}</code></p>
			</header>
		</div>
	);
}

export default App;
```

</div>

### Add CSS

Append to the end of `App.css`:

```
.clock {
  width: 350px;
  height: 350px;
  display: flex;
  justify-content: center;
  align-items: center;
  background: url("/public/clock.png");
  background-size: cover;
  border: 4px solid #091921;
  border-radius: 50%;
  box-shadow: 0px 0px 50px red;
  position: relative;
}

.clock::before {
  content: '';
  width: 15px;
  height: 15px;
  background: #777;
  border-radius: 50%;
  z-index: 100;
}

.hour {
  position: absolute;
  bottom: 175px;
  height: 95px;
  width: 10px;
  background-color: #777777;
  transform-origin: bottom center;
  transform: rotate(0deg);
}

.min {
  position: absolute;
  bottom: 175px;
  height: 120px;
  width: 7px;
  background-color: #777777;
  transform-origin: bottom center;
  transform: rotate(0deg);
}

.sec {
  position: absolute;
  bottom: 150px;
  height: 167px;
  width: 3px;
  background-color: red;
  transform-origin: center 142px;
  transform: rotate(0deg);
}
```

### Add Clock background image

Save this image inside the `public` folder as `clock.png`. **<a href="/images/analog-clock-using-reactJS-clock.png.png" download="clock.png">Download</a>**

![Clock background](https://github.com/skillsboy/react-analog-clock/raw/main/public/clock.png#center)

### End result

<a href="https://skillsboy.github.io/react-analog-clock/" target="_blank">Demo</a>

<a href="https://github.com/skillsboy/react-analog-clock" target="_blank">Source Code</a>

{{<endMessage>}}Have fun 😄{{</endMessage>}}