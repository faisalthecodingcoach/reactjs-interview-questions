# 500+ React.js Interview Questions and Answers To Land Your Next Six-Figure Job Offer as React.js Engineer - [React JS Mastery: Test Your Skills with Practice Tests 2023](https://www.udemy.com/course/react-js-mastery-test-your-skills-with-practice-tests-2023/?referralCode=4C16E7148CB248DB20AD) - 30 day money back guarantee and full lifetime access.

[React JS Mastery: Test Your Skills with Practice Tests 2023](https://www.udemy.com/course/react-js-mastery-test-your-skills-with-practice-tests-2023/?referralCode=4C16E7148CB248DB20AD) course is a biggest hand-picked collection of top technical React.js interview questions for junior and experienced web developers with more that 500+ interview questions and answers divided logically into 6 practice tests. Whether you're a job seeker, student, or experienced developer, React JS Mastery will prepare you to ace interviews, impress employers, and excel in your projects. Prepare for your next React.js interview and land a job offer in no time.

🔴 Get All 500+ Question & Answers on [React JS Mastery: Test Your Skills with Practice Tests 2023](https://www.udemy.com/course/react-js-mastery-test-your-skills-with-practice-tests-2023/?referralCode=4C16E7148CB248DB20AD)

[![Course Intro Video](https://img.youtube.com/vi/Di8ouLLMpNQ/0.jpg)](https://www.youtube.com/watch?v=Di8ouLLMpNQ)

## <a name='toc'>Table of Contents</a>

- [React.js Practice Test #1](#RP1)
- [Course Description](#CD)
- [Course FAQs](#FAQ)
- [React.js Practice Test #2](#RP2)
- [React.js Practice Test #3](#RP3)
- [React.js Practice Test #4](#RP4)
- [React.js Practice Test #5](#RP5)
- [React.js Practice Test #6](#RP6)

## [[⬆]](#toc) <a name=RP1>React.js</a> Practice Test #1

#### Q1: In React, is it safe to embed user input in JSX as shown in the code snippet below?

```
    const title = response.potentiallyMaliciousInput;
    //is this safe:
    const element = <h1>{title}</h1>;
```

**Answer:**
By default, `React DOM escapes` any values embedded in `JSX` before rendering them. Thus it ensures that you can `never` inject anything that’s not explicitly written in your application. Everything is converted to a `string` before being rendered. This helps `prevent XSS` (cross-site-scripting) attacks.

**Source:** _reactjs.org_

#### Q2: Is the element object shown in the code snippet below a valid React Element ?

```
    const element = {
        type: 'h1',
        props: {
            className: 'greeting',
            children: 'Hello, world!'
        }
    };
```

**Answer:**
**_YES_**, these objects are called “React elements”. You can think of them as descriptions of what you want to see on the screen. React reads these objects and uses them to construct the DOM and keep it up to date.

**Source:** _reactjs.org_

#### Q3: When the React component shown below has been initially rendered, you can trigger further re-renders from any event handler in it by:?

```
    import React, { useState, useRef } from 'react';

    const App = () => {
        const [name, setName] = useState('');
        const nameRef = useRef(null);

        .....
        .....
    }

    export default App;
```

A-) setting the ref as nameRef = ’new name’
B-) setting the ref as nameRef.current = ‘new name’
C-) setting the state variable as name = ‘new name’
D-) setting the state variable as setName(’new name’)

**Answer:**
**_D_**, Once the component has been initially rendered, you can trigger further renders by updating its state with the set function. Updating your component’s state automatically queues a render.

**Source:** _reactjs.org_

#### Q4: What will be the output inside of the <h1> tag on clicking the button labelled as “Increase the number” in the component below for the very first time?

```
    import { useState } from 'react';

    export default function Counter() {
    const [number, setNumber] = useState(0);

    return (
        <>
        <h1>{number}</h1>
        <button onClick={() => {
            setNumber(number + 5);
            setNumber(n => n + 1);
            setNumber(42);
        }}>Increase the number</button>
        </>
    )
    }
```

a-) 5 b-) 6 c-) 48 d-) 42

**Answer:**
**_d-)_**, 42. Here’s how React works through these lines of code while executing this event handler:

- 1. setNumber(number + 5): number is 0, so setNumber(0 + 5). React adds “replace with 5” to its queue.
- 2. setNumber(n => n + 1): n => n + 1 is an updater function. React adds that function to its queue.
- 3. setNumber(42): React adds “replace with 42” to its queue.
     Then React stores 42 as the final result and returns it from useState.

Then React stores 42 as the final result and returns it from useState.

**Source:** _reactjs.org_

#### Q5: On Clicking the Reverse button in the List component below, it will mutate the original state list array?

```
import { useState } from 'react';

let nextId = 3;
const initialList = [
  { id: 0, title: 'Big Bellies' },
  { id: 1, title: 'Lunar Landscape' },
  { id: 2, title: 'Terracotta Army' },
];

export default function List() {
  const [list, setList] = useState(initialList);

  function handleClick() {
    const nextList = [...list];
    nextList.reverse();
    setList(nextList);
  }

  return (
    <>
      <button onClick={handleClick}>
        Reverse
      </button>
      <ul>
        {list.map(artwork => (
          <li key={artwork.id}>{artwork.title}</li>
        ))}
      </ul>
    </>
  );
}
```

A-) True b-) False

**Answer:**
**_False_**, Clicking on the reverse button in the component above will not mutate the original list array since we are copying the original list to a separate variable prior to executing reverse on it and assigning it as a new array to the state setter function.

**Source:** _reactjs.org_

#### Q6: State of a React component is tied to it’s position in the UI tree?

A-) True B-) False

**Answer:**
**_True_**, When you give a component state, you might think the state “lives” inside the component. But the state is actually held inside React. React associates each piece of state it’s holding with the correct component by where that component sits in the UI tree.

**Source:** _reactjs.org_

#### Q7: On clicking the button labelled as “Click me!” for the very first time in the Counter component shown below, will alert: ?

```
import { useRef } from 'react';

export default function Counter() {
  let ref = useRef(0);

  function handleClick() {
    ref.current = ref.current + 1;
    alert('You clicked ' + ref.current + ' times!');
  }

  return (
    <button onClick={handleClick}>
      Click me!
    </button>
  );
}
```

A-) You clicked 0 times!  
B-) You clicked 1 times!  
C-) You clicked 2 times!  
D-) None of the above

**Answer:**
**_B-)_**, you can access the current value of that ref through the ref.current property. This value is intentionally mutable, meaning you can both read and write to it. It’s like a secret pocket of your component that React doesn’t track. In the code snippet above, a button will increment ref.current on every click, the component doesn’t re-render with every increment. Like state, refs are retained by React between re-renders. However, setting state re-renders a component. Changing a ref does not! Limitations of React state don’t apply to refs. For example, state acts like a snapshot for every render and doesn’t update synchronously. But when you mutate the current value of a ref, it changes immediately, that’s why you are getting the alert as “You clicked 1 times!” on clicking the button for the very first time in the component above.

**Source:** _reactjs.org_

#### Q8: In the component below, if we press “Send”, there is a small delay before the message is shown. For example if we type “Welcome” and press Send, and then quickly edit the input again. Despite our edits, the alert would still show “Welcome” (which was the value of state at the time the button was clicked). Usually, this behavior is what you want in an app. However what will be the best possible change you will make to this component to make the alert show the current input text rather than what it was at the time of the click?

```
import { useState } from 'react';

export default function Chat() {
  const [text, setText] = useState('');

  function handleSend() {
    setTimeout(() => {
      alert('Sending: ' + text);
    }, 3000);
  }

  function handleChange(e) {
	setText(e.target.value);
  }

  return (
    <>
      <input
        value={text}
        onChange={handleChange}
      />
      <button
        onClick={handleSend}>
        Send
      </button>
    </>
  );
}
```

A-)

```
import { useState } from 'react';

export default function Chat() {
  const [text, setText] = useState('');
  let currentText = '';

  function handleSend() {
    setTimeout(() => {
      alert('Sending: ' + currentText);
    }, 3000);
  }

  function handleChange(e) {
	setText(e.target.value);
    currentText += e.target.value;
  }

  return (
    <>
      ....
    </>
  );
}
```

B-)

```
import { useState } from 'react';

let currentText = '';
export default function Chat() {
  const [text, setText] = useState('');

  function handleSend() {
    setTimeout(() => {
      alert('Sending: ' + currentText);
    }, 3000);
  }

  function handleChange(e) {
	setText(e.target.value);
    currentText += e.target.value;
  }

  return (
    <>
      ....
    </>
  );
}
```

C-)

```
import { useState } from 'react';

export default function Chat() {
  const [text, setText] = useState('');
  const [currentText, setCurrentText] = useState('');
  function handleSend() {
    setTimeout(() => {
      alert('Sending: ' + currentText);
    }, 3000);
  }

  function handleChange(e) {
	setText(e.target.value);
    setCurrentText(e.target.value);
  }

  return (
    <>
		  ....
    </>
  );
}
```

D-)

```
import { useState, useRef } from 'react';

export default function Chat() {
  const [text, setText] = useState('');
  const currentTextRef = useRef(null);
  function handleSend() {
    setTimeout(() => {
      alert('Sending: ' + currentTextRef.current);
    }, 3000);
  }

  function handleChange(e) {
	setText(e.target.value);
    currentTextRef.current = e.target.value;
  }

  return (
    <>
      ....
    </>
  );
}
```

**Answer:**

**_D-_**, State works like a snapshot, so you can’t read the latest state from an asynchronous operation like a timeout. However, you can keep the latest input text in a ref. A ref is mutable, so you can read the current property at any time. Since the current text is also used for rendering, in this example, you will need both a state variable (for rendering), and a ref (to read it in the timeout). You will need to update the current ref value manually.

**Source:** _reactjs.org_

#### The code in the App component below will create a ref to each item in the fruits list?

```
import React, { useRef } from 'react';

const App = ()=> {
	const fruits = ['Apple', 'Banana', 'Orange', 'Pineapple', 'Guava'];

	return (
    <div>
			<h1>Fruits</h1>
			{
				fruits.map(fruit => {
					const ref = useRef(null);
					return <li key={fruit} ref={ref}>{fruit}</li>
				}
			)};
		</div>
	);
}
```

A-) True B-) False

**Answer:**
**_B-)_**, False. Sometimes you might need a ref to each item in the list, and you don’t know how many you will have. Something like in the code snippet above will not work. his is because Hooks must only be called at the top-level of your component. You can’t call useRef in a loop, in a condition, or inside a map() call. One possible way around this is to get a single ref to their parent element, and then use DOM manipulation methods like querySelectorAll to “find” the individual child nodes from it. However, this is brittle and can break if your DOM structure changes. Another solution is to pass a function to the ref attribute. This is called a ref callback. React will call your ref callback with the DOM node when it’s time to set the ref, and with null when it’s time to clear it. This lets you maintain your own array or a Map, and access any ref by its index or some kind of ID. For example:

```
<li
  key={cat.id}
  ref={node => {
    const map = getMap();
    if (node) {
      // Add to the Map
      map.set(cat.id, node);
    } else {
      // Remove from the Map
      map.delete(cat.id);
    }
  }}
>
```

**Source:** _reactjs.org_

#### Q11: What will happen when we click on the ‘Focus the input’ button in the App component shown below?

```
import React, { useRef } from 'react';

function MyInput(props) {
  return <input {...props} />;
}

export default function App() {
  const inputRef = useRef(null);

  function handleClick() {
    inputRef.current.focus();
  }

  return (
    <>
      <MyInput ref={inputRef} />
      <button onClick={handleClick}>
        Focus the input
      </button>
    </>
  );
}
```

A-) It will focus the <input/> DOM element inside of the MyInput component.
B-) It will throw a runtime error.
C-) It will not focus the <input/> DOM element inside of the MyInput component and will also not throw any errors.
D-) None of the above

**Answer:**
**_B-)_** It will throw a runtime error. Clicking the button above **does not** focus the input.

This happens because by default React does not let a component access the DOM nodes of other components. Not even for its own children! This is intentional. Refs are an escape hatch that should be used sparingly. Manually manipulating _another_ component’s DOM nodes makes your code even more fragile. Instead, components that _want_ to expose their DOM nodes have to **opt in** to that behavior. A component can specify that it “forwards” its ref to one of its children. Here’s how MyInput can use the forwardRef API.

**Source:** _reactjs.org_

#### Q12: In React. effects let you specify side effects that are caused by \***\*\_\_\_\_\*\***.

A-) a particular event B-) rendering itself C-) Both a & b D-) None of the above

**Answer:**
Effects let you specify side effects that are caused by rendering itself, rather than by a particular event. Effects run at the end of a commit after the screen updates. This is a good time to synchronize the React components with some external system (like network or a third-party library).

**Source:** _reactjs.org_

#### Q13: Which of the following statement is correct for the App component shown below?

```
import React, { useEffect } from "react";

export default function App() {

  useEffect(()=> {
    console.log('mounted');
    window.location.reload();
  }, []);

  return (
    <form>
      <input type="search" />
			<button>Search</button>
    </form>
  );
}
```

A-) In the production environment, the App component above will firstly get mounted, succeeded by an unmount and then will finally mount again and will be ready for the user interaction.

B-) In the production environment, the App component above will be mounting and unmounting infinitely.

C-) The useEffect inside the App component will never be executed and hence will have no effect on the app post rendering.

D-) None of the above

**Answer:**
**_B_**, In the production environment, the App component displayed above will be mounting and unmounting infinitely.

In the production environment, the App component above will be mounting and unmounting infinitely, since we are calling window.location.reload() method on mount of the above component and as a result it will cause the component to re-render infinitely.

**Source:** _reactjs.org_

#### Q14: Is ‘inputRef’ a required dependency inside the useEffect hook in the App component below? Can we remove it from the useEffect dependency array in the component below?

```
import { useState, useRef, useEffect } from 'react';

export default function App(){
  const [show, setShow] = useState(false);
  const inputRef = useRef(null);

  useEffect(()=>{
    if(show){
      inputRef.current.focus();
    }
  }, [show, inputRef]);

  return(
    <>
     {show && <input type="text" ref={inputRef} />}
     <button onClick={()=>{
      setShow(!show);
     }}>{show ? 'Hide' : 'Show'} Input</button>
    </>
  );
}
```

A-) It’s a required dependency and can’t be removed.
B-) It can be removed, since it never changes, so it will never by itself cause the Effect to re-run.
C-) It can be removed, however removing it will also remove the focus on show functionality.
D-) None of the above.

**Answer:**
Although the Effect uses both the show and the inputRef inside of it’s body, but only show is the required dependency for it to work as expected and we can omit the inputRef. This is because the ref object has a stable identity: React guarantees you’ll always get the same object from the same useRef call on every render. It never changes, so it will never by itself cause the Effect to re-run. Therefore, it does not matter whether you include it or not.

**Source:** _reactjs.org_

#### Q15: You’re writing a ChatRoom component that needs to connect to the chat server when it appears. You are given a createConnection() API that returns an object with connect() and disconnect() methods. Which one of the following is the most appropriate implementation for the ChatRoom Component?

A-)

```
import { useEffect } from 'react';
import { createConnection } from './chat.js';

export default function ChatRoom() {
  useEffect(() => {
    const connection = createConnection();
    connection.connect();

		return connection.disconnect();
  }, []);
  return <h1>Chat Now!</h1>;
}
```

B-)

```
import { useEffect } from 'react';
import { createConnection } from './chat.js';

export default function ChatRoom() {
  useEffect(() => {
    const connection = createConnection();
    window.addEventListener('load', ()=>connection.connect());
  }, []);
  return <h1>Chat Now!</h1>;
}
```

C-)

```
import { useEffect } from 'react';
import { createConnection } from './chat.js';

export default function ChatRoom() {
  useEffect(() => {
    const connection = createConnection();
    window.addEventListener('load', ()=>connection.connect());

  }, []);
  return <h1>Chat Now!</h1>;
}
```

D-)

```
import { useState, useEffect } from 'react';
import { createConnection } from './chat.js';

export default function ChatRoom() {
  useEffect(() => {
    const connection = createConnection();
    connection.connect();
    return () => connection.disconnect();
  }, []);
  return <h1>Welcome to the chat!</h1>;
}
```

**Answer:**
**_Option (d)_** is the most appropriate option for the implementation of the needed ChatRoom component. Since the cleanup is well implemented in it’s useEffect that ultimately prevents memory leaks and removes some unnecessary and unwanted behaviors.

**Source:** _reactjs.org_

#### Q16: In the development mode in React 18, which one of the following options will be logged for the initial mount of the ChatRoom Component shown below?

```
import { useState, useEffect } from 'react';
import { createConnection } from './chat.js';

export default function ChatRoom() {
  useEffect(() => {
    const connection = createConnection();
		console.log('Connecting...');
    connection.connect();
    return () => {
			console.log('Disconnected');
			connection.disconnect();
		}
  }, []);
  return <h1>Welcome to the chat!</h1>;
}
```

A-) Connecting…
Disconnected

B-) Connecting…
Connecting…
Disconnected

C-) Disconnected

D-) Connecting…
Disconnected
Connecting…

**Answer:**
**_Option (d)_**. React will call your cleanup function each time before the Effect runs again, and one final time when the component unmounts (gets removed). This is the correct behavior in development. By remounting your component, React verifies that navigating away and back would not break your code. Disconnecting and then connecting again is exactly what should happen! When you implement the cleanup well, there should be no user-visible difference between running the Effect once vs running it, cleaning it up, and running it again. There’s an extra connect/disconnect call pair because React is probing your code for bugs in development. This is normal—don’t try to make it go away! In production, you would only see "Connecting..." printed once. Remounting components only happens in development to help you find Effects that need cleanup. You can turn off Strict Mode to opt out of the development behavior, but it is recommend to keep it on.

**Source:** _reactjs.org_

#### Q17: The effect shown below will avoid race conditions and will ensure that the fetch requests that are not relevant anymore does not keep affecting your application?

```
useEffect(() => {
    const controller = new AbortController()

    fetch('https://jsonplaceholder.typicode.com/posts/1', {
        signal: controller.signal,
    })
        .then(res => res.json())
        .then(json => setMessage(json.title))
        .catch(error => {
            if (error.name !== 'AbortError') {
                console.error(error.message)
            }
        })
}, [])
```

A-) TRUE B-) FALSE

**Answer:**
**_Option (b)_**. False, since it’s missing the cleanup -

```
return () => controller.abort()
```

**Source:** _reactjs.org_

#### Q18: The App component shown below renders two <MyInput /> components. Each <MyInput /> component focuses an input field on mount. Please select the statement that hold’s true regarding the focusing of the two rendered input fields -

```
import React, { useRef, useEffect } from "react";

export default function App() {
  return (
    <form>
      <MyInput />
      <MyInput />
    </form>
  );
}

const MyInput = ()=>{
  const myInputRef = useRef(null);

  useEffect(()=>{
    myInputRef.current.focus();
  }, [])

  return <input ref={myInputRef} />
}
```

A-) Both of the input fields will be focussed on mount.
B-) Only the first input field will be focussed.
C-) Only the last input field will be focussed.
D-) Only one input field will be displayed on the screen and it will be focussed.

**Answer:**
**_Option (c)_**. Only the the last field automatically gets focused. This is because both of the <MyInput /> components try to focus the field inside. When you call focus() for two input fields in a row, the last one always “wins”.

**Source:** _reactjs.org_

#### Q19: To transform data for rendering, for example, let’s say we want to filter a list before displaying it we shall \***\*\*\*\*\***\_\_\_\***\*\*\*\*\*** -

A-) do it inside of an effect.
B-) transform all the data at the top level of my components, outside of any effects.
C-) do it inside of a cleanup function of an effect.
d-) none of the above

**Answer:**
**_Option (b)_**. You don’t need Effects to transform data for rendering. For example, let’s say you want to filter a list before displaying it. You might feel tempted to write an Effect that updates a state variable when the list changes. However, this is inefficient. When you update the state, React will first call your component functions to calculate what should be on the screen. Then React will “commit” these changes to the DOM, updating the screen. Then React will run your Effects. If your Effect also immediately updates the state, this restarts the whole process from scratch! To avoid the unnecessary render passes, transform all the data at the top level of your components. That code will automatically re-run whenever your props or state change.

**Source:** _reactjs.org_

### Q20: The App component below contains a sign up form that send’s a POST request to the /api/signup endpoint. Will you recognize it’s current implementation as the best practice to make such API requests?

```
import React from 'react';

export default function App() {
  const [firstName, setFirstName] = useState('');
  const [lastName, setLastName] = useState('');
	const [email, setEmail] = useState('');
  const [formDataToSubmit, setFormDataToSubmit] = useState(null);

  useEffect(() => {
    if (formDataToSubmit !== null) {
	    post('/api/signup', {
				method: 'POST',
				headers: {
		     'Content-Type': 'application/json'
		    },
				body: JSON.stringify(formDataToSubmit)
			});
    }
  }, [formDataToSubmit]);

  function handleSubmit(e) {
    e.preventDefault();
    setFormDataToSubmit({ firstName, lastName, email });
  }
  // ...
}
```

A-) True
B-) False

**Answer:**
**_Option (b)_**. False. You don’t need Effects to handle user events. For example, The App component below contains a sign up form that send’s a POST request to the /api/signup endpoint. In the Submit button click event handler, you know exactly what happened. By the time an Effect runs, you don’t know what the user did (for example, which button was clicked). This is why you’ll usually handle user events in the corresponding event handlers.

**Source:** _reactjs.org_

#### 70 more questions in the React.js Practice Test #1

Attempt them now at 👉 <a href='https://www.udemy.com/course/react-js-mastery-test-your-skills-with-practice-tests-2023/?referralCode=4C16E7148CB248DB20AD'>udemy.com/course/react-js-mastery-test-your-skills-with-practice-tests-2023</a>

## [[⬆]](#toc) <a name=CD>React JS Mastery: Test Your Skills with Practice Tests 2023 - Course Description</a>

Read course description at 👉 <a href='https://reactjsmastery.mohdfaisal.com/#course-intro'>Course Description</a>

## [[⬆]](#toc) <a name=FAQ>React JS Mastery: Test Your Skills with Practice Tests 2023 - FAQs</a>

Read the course FAQs section here 👉 <a href='https://reactjsmastery.mohdfaisal.com/#faq'>FAQs</a>

## [[⬆]](#toc) <a name=RP2>React.js</a> Practice Test #2

#### 80 hand picked interview questions in the React.js Practice Test #2

Attempt them now at 👉 <a href='https://www.udemy.com/course/react-js-mastery-test-your-skills-with-practice-tests-2023/?referralCode=4C16E7148CB248DB20AD'>udemy.com/course/react-js-mastery-test-your-skills-with-practice-tests-2023</a>

## [[⬆]](#toc) <a name=RP3>React.js</a> Practice Test #3

#### 80 hand picked interview questions in the React.js Practice Test #3

Attempt them now at 👉 <a href='https://www.udemy.com/course/react-js-mastery-test-your-skills-with-practice-tests-2023/?referralCode=4C16E7148CB248DB20AD'>udemy.com/course/react-js-mastery-test-your-skills-with-practice-tests-2023</a>

## [[⬆]](#toc) <a name=RP4>React.js</a> Practice Test #4

#### 80 hand picked interview questions in the React.js Practice Test #4

Attempt them now at 👉 <a href='https://www.udemy.com/course/react-js-mastery-test-your-skills-with-practice-tests-2023/?referralCode=4C16E7148CB248DB20AD'>udemy.com/course/react-js-mastery-test-your-skills-with-practice-tests-2023</a>

## [[⬆]](#toc) <a name=RP5>React.js</a> Practice Test #5

#### 80 hand picked technical interview questions in the React.js Practice Test #5

Attempt them now at 👉 <a href='https://www.udemy.com/course/react-js-mastery-test-your-skills-with-practice-tests-2023/?referralCode=4C16E7148CB248DB20AD'>udemy.com/course/react-js-mastery-test-your-skills-with-practice-tests-2023</a>

## [[⬆]](#toc) <a name=RP6>React.js</a> Practice Test #6

#### 95 hand picked technical interview questions in the React.js Practice Test #6

Attempt them now at 👉 <a href='https://www.udemy.com/course/react-js-mastery-test-your-skills-with-practice-tests-2023/?referralCode=4C16E7148CB248DB20AD'>udemy.com/course/react-js-mastery-test-your-skills-with-practice-tests-2023</a>
