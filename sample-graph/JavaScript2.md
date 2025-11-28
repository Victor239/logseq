### Web development
	- ### React
		- Next.js uses Node JavaScript runtime (alternatives include Deno, Bun) in order to implement features like Static Site Generation. However browser-based JavaScript engines like V8, Gecko, WebKit also have access Web APIs, which runtimes like Node.js will never implement
		  collapsed:: true
			- Because Next.js has no access to Web APIs from the Node.js runtime this means some of their features have limited support for Web APIs e.g. Static Site Generation can have issues with Web Workers
			- LLM:
				- **Node.js and Deno** are *runtimes*: they use a JavaScript engine like V8 to run code, but crucially, they also provide system APIs for file system access, networking, and more.[](https://betterstack.com/community/guides/scaling-nodejs/nodejs-vs-deno-vs-bun/)
				- **V8 and Gecko** are *engines*: they simply parse, compile, and run JavaScript. Gecko includes SpiderMonkey as its JS engine.[](https://stackoverflow.com/questions/29027845/what-is-the-difference-between-javascript-engine-and-javascript-runtime-environm)
				- **Node.js** uses V8 (the engine from Chrome), Deno uses V8 as well. **Gecko** itself is Mozilla’s browser rendering engine, with **SpiderMonkey** as its JavaScript engine
		- By version
		  collapsed:: true
			- 19.2
				- `useEffectEvent` for separating event logic from event dependencies
				- partial pre-rendering
		- [Next.js pros/cons](https://news.ycombinator.com/item?id=45099922)
		- assuming a ReactNode with two methods and just returns a <div>, how to pass those two methods to another file to utilise the methods on that component
		  collapsed:: true
			- Your component file — expose methods via a ref
			  logseq.order-list-type:: number
				- ```typescript
				  // MyRecorder.tsx
				  import React, { useImperativeHandle, useRef, forwardRef } from "react";
				  
				  export interface MyRecorderRef {
				    start: () => void;
				    stop: () => void;
				  }
				  
				  const MyRecorder = forwardRef<MyRecorderRef>((_, ref) => {
				    const divRef = useRef<HTMLDivElement>(null);
				  
				    // internal methods
				    const start = () => {
				      console.log("Started recording!");
				    };
				  
				    const stop = () => {
				      console.log("Stopped recording!");
				    };
				  
				    // expose them through the ref
				    useImperativeHandle(ref, () => ({
				      start,
				      stop
				    }));
				  
				    return <div ref={divRef}>Recorder UI here</div>;
				  });
				  
				  export default MyRecorder;
				  
				  ```
			- In another file — use those methods
			  logseq.order-list-type:: number
				- ```typescript
				  // App.tsx
				  import React, { useRef } from "react";
				  import MyRecorder, { MyRecorderRef } from "./MyRecorder";
				  
				  export default function App() {
				    const recorderRef = useRef<MyRecorderRef>(null);
				  
				    const handleStart = () => {
				      recorderRef.current?.start();
				    };
				  
				    const handleStop = () => {
				      recorderRef.current?.stop();
				    };
				  
				    return (
				      <div>
				        <MyRecorder ref={recorderRef} />
				        <button onClick={handleStart}>Start</button>
				        <button onClick={handleStop}>Stop</button>
				      </div>
				    );
				  }
				  ```
		- State
			- Passing state
			  collapsed:: true
				- Prop drilling
				- [useContext](https://react.dev/reference/react/useContext)
					- [Passing Data Deeply with Context – React](https://react.dev/learn/passing-data-deeply-with-context)
					  collapsed:: true
						- Example 1
							- `Section.js`
							  ```javascript
							  export default function Section({ children }) {
							    return (
							      <section className="section">
							        {children}
							      </section>
							    );
							  }
							  ```
							- `App.js`
							  ```javascript
							  import Heading from './Heading.js';
							  import Section from './Section.js';
							  
							  export default function Page() {
							    return (
							      <Section>
							        <Heading level={1}>Title</Heading>
							        <Heading level={2}>Heading</Heading>
							        <Heading level={3}>Sub-heading</Heading>
							        <Heading level={4}>Sub-sub-heading</Heading>
							        <Heading level={5}>Sub-sub-sub-heading</Heading>
							        <Heading level={6}>Sub-sub-sub-sub-heading</Heading>
							      </Section>
							    );
							  }
							  ```
							- `Heading.js`
							  ```javascript
							  export default function Heading({ level, children }) {
							    switch (level) {
							      case 1:
							        return <h1>{children}</h1>;
							      case 2:
							        return <h2>{children}</h2>;
							      case 3:
							        return <h3>{children}</h3>;
							      case 4:
							        return <h4>{children}</h4>;
							      case 5:
							        return <h5>{children}</h5>;
							      case 6:
							        return <h6>{children}</h6>;
							      default:
							        throw Error('Unknown level: ' + level);
							    }
							  }
							  ```
					- Example
					  collapsed:: true
						- 1) Create the context
							- ```typescript
							  import React, { createContext, useContext } from "react";
							  
							  // Define the shape of the context
							  interface MyFunctionsContextType {
							    functionA: () => void;
							    functionB: () => void;
							  }
							  
							  // Create context with default empty functions
							  const MyFunctionsContext = createContext<MyFunctionsContextType>({
							    functionA: () => {},
							    functionB: () => {},
							  });
							  
							  ```
						- 2) Provide the context
							- ```typescript
							  export const MyComponent: React.FC = () => {
							    const functionA = () => {
							      console.log("Function A called");
							    };
							  
							    const functionB = () => {
							      console.log("Function B called");
							    };
							  
							    return (
							      <MyFunctionsContext.Provider value={{ functionA, functionB }}>
							        <p>test</p>
							      </MyFunctionsContext.Provider>
							    );
							  };
							  ```
						- 3) Consume the context in another component
							- ```typescript
							  import React from "react";
							  import { MyFunctionsContext } from "./MyComponent"; // adjust import path
							  
							  export const AnotherComponent: React.FC = () => {
							    const { functionA, functionB } = useContext(MyFunctionsContext);
							  
							    return (
							      <div>
							        <button onClick={functionA}>Call Function A</button>
							        <button onClick={functionB}>Call Function B</button>
							      </div>
							    );
							  };
							  ```
					- Example 2
					  collapsed:: true
						- New structure
							- ```
							  RemoteControl
							   └── RecorderProvider   ← owns state + methods + context
							          ├── CommandBar
							          └── VideoContainer
							  ```
						- `recorder-context.tsx`
							- ```tsx
							  import { createContext } from "react";
							  import React, { useCallback, useState } from "react";
							  
							  interface RecorderContextValue {
							    recording: boolean;
							    setRecording: React.Dispatch<React.SetStateAction<boolean>>;
							    startRecording: () => void;
							    stopRecording: () => void;
							  }
							  
							  const RecorderContext = createContext<RecorderContextValue | null>(null);
							  
							  export const RecorderProvider: React.FC<{ children: React.ReactNode }> = ({ children }) => {
							    const [recording, setRecording] = useState(false);
							  
							    const startRecording = useCallback(() => {
							      console.log("start recording");
							      setRecording(true);
							    }, []);
							  
							    const stopRecording = useCallback(() => {
							      console.log("stop recording");
							      setRecording(false);
							    }, []);
							  
							    return (
							      <RecorderContext.Provider
							        value={{ recording, setRecording, startRecording, stopRecording }}
							      >
							        {children}
							      </RecorderContext.Provider>
							    );
							  };
							  ```
						- `video-container.tsx`
						  Uses `useContext`
							- ```tsx
							  import React, { useContext } from "react";
							  import { RecorderContext } from "./recorder-context";
							  
							  export const VideoContainer: React.FC = () => {
							    const ctx = useContext(RecorderContext);
							    if (!ctx) return null;
							  
							    return (
							      <div>
							        <h3>Video Container</h3>
							        <p>Recording: {ctx.recording ? "YES" : "NO"}</p>
							      </div>
							    );
							  };
							  ```
						- `command-bar.tsx`
						  Uses `useContext`
							- ```tsx
							  import React, { useContext } from "react";
							  import { RecorderContext } from "./recorder-context";
							  
							  export const CommandBar: React.FC = () => {
							    const ctx = useContext(RecorderContext);
							    if (!ctx) return null;
							  
							    return (
							      <div>
							        <button onClick={ctx.startRecording} disabled={ctx.recording}>
							          Start
							        </button>
							  
							        <button onClick={ctx.stopRecording} disabled={!ctx.recording}>
							          Stop
							        </button>
							      </div>
							    );
							  };
							  ```
						- `remote-control.tsx`
						  RemoteControl wraps siblings with the provider
							- ```tsx
							  import React from "react";
							  import { RecorderProvider } from "./recorder-provider";
							  import { CommandBar } from "./command-bar";
							  import { VideoContainer } from "./video-container";
							  
							  export const RemoteControl: React.FC = () => {
							    return (
							      <RecorderProvider>
							        <div>
							          <CommandBar />
							          <VideoContainer />
							        </div>
							      </RecorderProvider>
							    );
							  };
							  ```
				- Global state hook
				  collapsed:: true
					- It can
						- store and update shared state
						- be accessed and modified from any component via a simple `useGlobalState()` hook
					- 1) Create the context + provider
						- ```typescript
						  // GlobalStateContext.tsx
						  import React, { createContext, useContext, useState, ReactNode } from "react";
						  
						  // 1️⃣ Define types
						  interface GlobalStateContextType {
						    count: number;
						    setCount: React.Dispatch<React.SetStateAction<number>>;
						  }
						  
						  // 2️⃣ Create the context
						  const GlobalStateContext = createContext<GlobalStateContextType | undefined>(undefined);
						  
						  // 3️⃣ Create a provider component
						  export const GlobalStateProvider = ({ children }: { children: ReactNode }) => {
						    const [count, setCount] = useState(0);
						  
						    return (
						      <GlobalStateContext.Provider value={{ count, setCount }}>
						        {children}
						      </GlobalStateContext.Provider>
						    );
						  };
						  
						  // 4️⃣ Create the custom hook to use the context
						  export const useGlobalState = () => {
						    const context = useContext(GlobalStateContext);
						    if (!context) {
						      throw new Error("useGlobalState must be used within a GlobalStateProvider");
						    }
						    return context;
						  };
						  ```
					- 2) Wrap your app with the provider
						- ```typescript
						  // App.tsx
						  import React from "react";
						  import { GlobalStateProvider } from "./GlobalStateContext";
						  import Counter from "./Counter";
						  import IncrementButton from "./IncrementButton";
						  
						  export default function App() {
						    return (
						      <GlobalStateProvider>
						        <div className="p-4">
						          <Counter />
						          <IncrementButton />
						        </div>
						      </GlobalStateProvider>
						    );
						  }
						  ```
					- 3) Use the shared state anywhere
						- ```typescript
						  // Counter.tsx
						  import React from "react";
						  import { useGlobalState } from "./GlobalStateContext";
						  
						  export default function Counter() {
						    const { count } = useGlobalState();
						    return <div>Current count: {count}</div>;
						  }
						  ```
			- MobX cont
			  id:: 691c5a40-4559-4f44-8128-01eb4b52b3dd
			  collapsed:: true
				- `observable.box`
				  collapsed:: true
					- id:: 691c5b38-d28c-4c55-8f3b-f7353f86a10f
					  ```typescript
					  import { observable } from "mobx";
					  
					  export class SL {
					    readonly #totalSize = observable.box(0);
					  }
					  ```
						- **`#totalSize` is a *private* class field**
							- The `#` syntax means:
								- it is **true private** (ES private field)
								- **cannot** be accessed outside the class
									- (even by subclasses, unlike `private` in TS)
							- ```typescript
							  sl.#totalSize     // ❌ syntax error — illegal access
							  ```
						- `readonly` means you cannot reassign the field
							- Example
								- ```typescript
								  this.#totalSize.set(123);    // allowed
								  this.#totalSize = observable.box(5);  // ❌ cannot reassign because readonly
								  ```
							- Readonly protects the *reference*, not the internal MobX value.
						- `observable.box(0)` creates a MobX observable value
						  id:: 691caca5-0fc0-4bc0-9b03-dea7f91240a7
							- MobX has two ways to create observable state:
								- **observable objects** → `observable({ a: 1 })`
								- **observable boxed values** → `observable.box(value)`
							- A "boxed observable" is a simple observable container for primitive values.
							- It behaves like:
								- ```typescript
								  const x = observable.box(0);
								  
								  x.get();  // returns current value
								  x.set(5); // updates value and notifies observers
								  ```
							- So in your class:
								- ```typescript
								  #totalSize = observable.box(0);
								  ```
								- means:
									- the internal value starts at **0**
									- it is observable — reactions and computed values can track it
									- it can be changed internally via `.set()`
						- Why use `observable.box()` in a class?
							- MobX normally turns class fields into observables automatically only when using:
								- ```typescript
								  makeAutoObservable(this)
								  ```
							- But here you're explicitly creating a boxed observable yourself, which gives precise control.
				- https://search.brave.com/search?q=mobx+tutorial
				  collapsed:: true
					- [MobX: Ten minute introduction to MobX and React](https://mobx.js.org/getting-started)
						- ![overview.png](../assets/overview_1763724712350_0.png){:height 487, :width 658}
							- State
								- e.g. primitives, objects. These are the "data cells" of your spreadsheet
				- Example state pattern
				  id:: 69204f3d-4467-45cf-8586-5c03b52338ff
					- `_app.tsx`
						- ```tsx
						  const App = (props: AppProps): ReactNode => {
						    const state = useLocalObservable(() => new GlobalState());
						  }
						  ```
					- `global.ts`
					  id:: 69207dd7-4f22-4fb7-a3f5-156a99d40016
						- ```tsx
						  export class GlobalState {
						    readonly ad: AdState;
						    readonly dialog: DialogState;
						    readonly log: LogState;
						    
						    constructor() {
						      makeAutoObservable(this);
						      this.ad = new AdState();
						      this.dialog = new DialogState();
						      this.log = new LogState();
						    }
						  }
						  ```
					- Component1
						- `src/components/s/state.ts`
						  collapsed:: true
							- ```tsx
							  export class ScState {
							    readonly #width = observable.box(0);
							    readonly #client = observable.box<AdbScrcpyClient | undefined>();
							    readonly #disposers: IReactionDisposer[] = [];
							    
							    constructor(device: Adb, dialog: DialogState) {
							      // Asynchronous functions run in JavaScript micro-tasks and hence not in the
							      // cotext of the MobX `action` in which they would be declared by 
							      // `makeAutoObservable`. Instead we choose to withold them from being
							      // actions and manually call `runInAction` where observable state is mutated.
							      makeAutoObservable(this, {
							        start: action.bound,
							        stop: action.bound,
							        dispose: action.bound,
							        clientPositionToDevicePosition: false
							      });
							      
							      this.#disposers.push(
							        autorun(() => {
							          const decoder = this.#video.get()?.deoder;
							          if (this.rendererContainer && decoder) {
							            while (this.rendererContainer.firstChild) {
							              this.rendererContainer.firstChild.remove();
							            }
							            this.rendererContainer?.appendChild(decoder.renderer);
							            if (this.settings.server.video || this.settings.server.audio) {
							              runInAction(() => {
							                this.#recorder.set(
							                  new RecorderState(
							                    this.#device,
							                    decoder.renderer as HTMLCanvasElement,
							                  )
							                )
							              })
							            }
							          }
							        })
							      
							      this.#disposers.push(
							        autorun(() => {
							        if (this.#device) {
							          if (this.initial && this.visible) {
							            this.initial = false;
							            this.loadFiles();
							          }
							        } else {
							          this.initial = true;
							        }
							      })
							      )
							    }
							    
							    async start() {
							        try {
							          if (!this.settings.client.decoder) {
							            throw new Error("Failed to start remote control: No available decoder");
							          }
							  
							          runInAction(async () => {
							            this.#isConnecting.set(true);
							            this.#serverLoader.set(new ServerLoader(this.#device));
							          })
							        } 
							    };
							  }
							  ```
					- Component2
						- ```tsx
						  const Logcat: NextPage<AdDeviceSlice & DialogSlice> = (
						    props: AdDeviceSlice & DialogSlice,
						  ): ReactNode => {
						    const { device, dialog } = props;
						    const state = useLocalObservable(() => new LogcatState(device, dialog));
						  }
						  ```
						- ```tsx
						  export interface LogcatSlice {
						    logcat: LogcatState;
						  }
						  ```
						- ```tsx
						  export class LogcatState {
						    #dialog: DialogState;
						    #logcat: Logcat;
						    
						    constructor(device: Ad, dialog: DialogState) {
						      makeAutoObservable(this, {
						        buffer: false,
						        list: observable: shallow,
						        flush: action.bound,
						      });
						      
						      this.#logcat = new Logcat(device);
						      this.#dialog = dialog;
						    }
						  }
						  ```
						- Related: ((692081be-dc3f-492e-85b2-7e3b3dd18df0))
			- Slices pattern
			  id:: 692081be-dc3f-492e-85b2-7e3b3dd18df0
			  collapsed:: true
				- Concept from Redux
				- Example
					- A component
					  ```tsx
					  const RemoteControl: NextPage<AdDeviceSlice & DialogSlice> = (
					    props: AdDeviceSlice & DialogSlice
					  ): ReactNode => {
					    // etc
					  }
					  ```
					- ((69207dd7-4f22-4fb7-a3f5-156a99d40016))
					- `src/state/dialog.ts`
						- ```tsx
						  type DialogProps = DialogSlice;
						  
						  interface DialogProps {
						    level: DialogLevel;
						    content: ReactNode;
						  }
						  
						  export class DialogState {
						    readonly #props = observable.box<DialogProps | null>(null);
						    
						    constructor() {
						      makeAutoObservable(this);
						    }
						    
						    get props(): DialogProps | null {
						      return this.#props.get();
						    }
						  }
						  
						  export interface DialogSlice {
						    dialog: DialogState;
						  }
						  ```
				- Related: ((691c5a40-4559-4f44-8128-01eb4b52b3dd)) : ((69204f3d-4467-45cf-8586-5c03b52338ff))
		- How to extend a component so that you can pass additional props
		  collapsed:: true
			- Intersection example with one extra prop
				- ```typescript
				  interface ExtendedCommandBarProps extends ICommandBarProps {
				    func?: () => void; // your extra prop
				  }
				  
				  const ExtendedCommandBar: React.FC<ExtendedCommandBarProps> = (props) => {
				    return <CommandBar {...props} />;
				  };
				  
				  // Usage
				  <ExtendedCommandBar
				    items={items} // default prop available on ICommandBarProps
				    func={startStop}
				  />
				  ```
			- With arbitrary amount of extra props
				- ```typescript
				  interface ExtendedCommandBarProps extends ICommandBarProps {
				    extraProps?: Record<string, any>;
				  }
				  
				  const ExtendedCommandBar: React.FC<ExtendedCommandBarProps> = (props) => {
				    return <CommandBar {...props} />;
				  };
				  
				  // Usage
				  <ExtendedCommandBar
				    items={items} // default prop available on ICommandBarProps
				    func={startStop}
				  />
				  ```
		- [Hooks](https://react.dev/reference/react/hooks)
		  collapsed:: true
			- Sorted by importance
				- [useState](https://react.dev/reference/react/useState)
				- [useEffect](https://react.dev/reference/react/useEffect)
				- [useContext](https://react.dev/reference/react/useContext)
				- [useRef](https://react.dev/reference/react/useRef)
				- [useReducer – React](https://react.dev/reference/react/useReducer)
			- Sorted alphabetically
		- Microsoft's Fluent UI component library
		  collapsed:: true
			- Griffel is Microsoft’s CSS-in-JS solution used in Fluent UI v9
				- `makeStyles` lets you create CSS classes in JavaScript/TypeScript
					- ```jsx
					  import { makeStyles, mergeClasses } from "@griffel/react";
					  
					  const useStyles = makeStyles({
					    root: {
					      backgroundColor: "red",
					      padding: "10px",
					    },
					    active: {
					      backgroundColor: "green",
					    },
					  });
					  
					  ```
					- Then in a component:
						- ```jsx
						  const styles = useStyles();
						  
						  return <div className={styles.root}>Hello</div>;
						  ```
					- Griffel generates CSS behind the scenes and gives you:
						- predictable class names
						- atomic CSS
						- fast runtime performance
				- `mergeClasses` combines multiple class names into a single className string, dealing with overrides correctly.
					- ```jsx
					  import { mergeClasses } from "@griffel/react";
					  
					  <div className={mergeClasses(styles.root, isActive && styles.active)}>
					  ```
					- This is similar to `clsx` or `classnames`, but works with Griffel’s atomic classes so overrides resolve in the right order.
		- Remember when using `onClick` to wrap statements in an arrow function so that it doesn't run on component loading
		  collapsed:: true
			- ```tsx
			  return <Link onClick={() => setHintHidden("true")}>{`Don't show again`}</Link>
			  ```
		- TSX
		  id:: 692082d7-cd69-4304-a56a-d946bf931563
		  collapsed:: true
			- ```ts
			  readonly #props = observable.box<DialogProps | null>(null);
			  ```
				-
			- Related:
	- ### CSS
		- [Least amount of CSS needed for a good design](https://thecascade.dev/article/least-amount-of-css/)
		  collapsed:: true
			- ```css
			  html {
			    color-scheme: light dark;
			  }
			  
			  body {
			    font-family: system-ui;
			    font-size: 1.25rem;
			    line-height: 1.5;
			  }
			  
			  img,
			  svg,
			  video {
			    max-width: 100%;
			    display: block;
			  }
			  
			  main {
			    max-width: min(70ch, 100% - 4rem);
			    margin-inline: auto;
			  }
			  ```
		- CSS units cheatsheet
		  collapsed:: true
			- `px`: Absolute pixel value
			- `rem`: Relative to the [`font-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size) of the root element
			- `em`: Relative to the [`font-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size) of the element
			- `%`: Relative to the parent element
			- `vw`: Relative to the viewport's width, `1vw` = `1%` * viewport width
			- `vh`: Relative to the viewport's height, `1vh` = `1%` * viewport height
			- `vmin`: Relative to the viewport's smaller dimension, `1vmin` = min(`1vh`, `1vw`)
			- `vmax`: Relative to the viewport's larger dimension, `vmax` = max(`1vh`, `1vw`)
			- `ch`: Relative to the width of the glyph "0" of the element's font
			- [`in`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/in): Inches `1in` = `2.54cm` = `96px`
			- `pc`: Picas `1pc` = `1in` / `6` = `16px`
			- `pt`: Points `1pt` = `1in` / `72` = `1.333px` (approximately)
			- `cm`: Centimeters `1cm` = `96px` / `2.54` = `37.8px` (approximately)
			- `mm`: Millimeters `1mm` = `1cm` / `10` = `3.78px` (approximately)
		- `currentColor` property
		  collapsed:: true
			- Older keyword, precedes custom properties
			- `currentColor` contains the current value of the `color` property of the element. It is useful when you want to use the same color for multiple properties, such as `border-color` or `background-color`. It also respects the cascade, so if no value is provided for `color`, it will use the value of the `color` property of the parent element.
			- ```css
			  <p>My <span>background</span> is the same color as my <a href="#">text</a>.</p>
			  
			  p {
			    color: #101010;
			  }
			  
			  p, p > * {
			    background-color: currentColor;
			  }
			  
			  a {
			    color: #0077ff;
			  }
			  
			  span {
			    color: #fd203a;
			  }
			  ```
		- [CSS - Style links without a class - 30 seconds of code](https://www.30secondsofcode.org/articles/s/css-style-default-links)
		  collapsed:: true
			- When styling injected or generated HTML content, you might not have access to the classes or IDs of the elements you want to style. This can become especially annoying when dealing with link elements. Luckily, you can use the `:not()` selector with an appropriate attribute selector to check for the absence of a class and style links accordingly
			- ```css
			  a[href]:not([class]) {
			  color: #0077ff;
			  text-decoration: underline;
			  }
			  ```
		- [CSS inherited properties cheatsheet](https://www.30secondsofcode.org/articles/s/css-inherited-properties-cheatsheet)
		  collapsed:: true
			- `border-collapse`
			- `border-spacing`
			- `caption-side`
			- `color`
			- `cursor`
			- `direction`
			- `empty-cells`
			- `font-family`
			- `font-size`
			- `font-style`
			- `font-variant`
			- `font-weight`
			- `font-size-adjust`
			- `font-stretch`
			- `font`
			- `letter-spacing`
			- `line-height`
			- `list-style-image`
			- `list-style-position`
			- `list-style-type`
			- `list-style`
			- `orphans`
			- `quotes`
			- `tab-size`
			- `text-align`
			- `text-align-last`
			- `text-decoration-color`
			- `text-indent`
			- `text-justify`
			- `text-shadow`
			- `text-transform`
			- `visibility`
			- `white-space`
			- `widows`
			- `word-break`
			- `word-spacing`
			- `word-wrap`
		- Hide empty elements with no content
		  collapsed:: true
			- Use the `:empty` pseudo-class to select elements with no content.
			- ```css
			  <p>Lorem ipsum dolor sit amet. <button></button></p>
			  
			  :empty {
			    display: none;
			  }
			  ```
		- CSS - How can I ensure the footer is always at the bottom of the page
		  collapsed:: true
			- Assuming this is your HTML
				- ```html
				  <body>
				    <main></main>
				    <footer></footer>
				  </body>
				  ```
			- Either use
				- Flexbox
				  ```css
				  body {
				    min-height: 100vh;
				    display: flex;
				    flex-direction: column;
				  }
				  
				  footer {
				    margin-top: auto;
				  }
				  ```
				- CSS Grid
				  ```css
				  body {
				    min-height: 100vh;
				    display: grid;
				    grid-template-rows: 1fr auto;
				  }
				  ```
		- Displays an error message when an image fails to load
		  collapsed:: true
			- Aspects
				- Apply styles to the `img` element as if it was a text container.
				- Use the `::before` and `::after` pseudo-elements to display an error message and the image URL. These elements will only be displayed if the image fails to load
			- ```css
			  <img src="https://nowhere.to.be/found.jpg" />
			  
			  img {
			    display: block;
			    font-family: sans-serif;
			    font-weight: 300;
			    height: auto;
			    line-height: 2;
			    position: relative;
			    text-align: center;
			    width: 100%;
			  }
			  
			  img::before {
			    content: "Sorry, this image is unavailable.";
			    display: block;
			    margin-bottom: 8px;
			  }
			  
			  img::after {
			    content: "(url: " attr(src) ")";
			    display: block;
			    font-size: 12px;
			  }
			  ```
		- Custom styled radio button with animation on state change
		  collapsed:: true
			- Create a `.radio-container` and use flexbox to create the appropriate layout for the radio buttons.
			- Reset the styles on the `<input>` and use it to create the outline and background of the radio button.
			- Use the `::before` element to create the inner circle of the radio button.
			- Use `transform: scale(1)` and a CSS transition to create an animation effect on state change
			- ```css
			  <div class="radio-container">
			    <input class="radio-input" id="apples" type="radio" name="fruit" />
			    <label class="radio" for="apples">Apples</label>
			    <input class="radio-input" id="oranges" type="radio" name="fruit" />
			    <label class="radio" for="oranges">Oranges</label>
			  </div>
			  
			  .radio-container {
			    box-sizing: border-box;
			    background: #ffffff;
			    color: #222;
			    height: 64px;
			    display: flex;
			    justify-content: center;
			    align-items: center;
			    flex-flow: row wrap;
			  }
			  
			  .radio-container * {
			    box-sizing: border-box;
			  }
			  
			  .radio-input {
			    appearance: none;
			    background-color: #ffffff;
			    width: 16px;
			    height: 16px;
			    border: 1px solid #cccfdb;
			    margin: 0;
			    border-radius: 50%;
			    display: grid;
			    align-items: center;
			    justify-content: center;
			    transition: all 0.3s ease;
			  }
			  
			  .radio-input::before {
			    content: "";
			    width: 6px;
			    height: 6px;
			    border-radius: 50%;
			    transform: scale(0);
			    transition: 0.3s transform ease-in-out;
			    box-shadow: inset 6px 6px #ffffff;
			  }
			  
			  .radio-input:checked {
			    background: #0077ff;
			    border-color: #0077ff;
			  }
			  
			  .radio-input:checked::before {
			    transform: scale(1);
			  }
			  
			  .radio {
			    cursor: pointer;
			    padding: 6px 8px;
			  }
			  
			  .radio:not(:last-child) {
			    margin-right: 6px;
			  }
			  ```
		- [An interactive guide to SVG paths | Hacker News](https://news.ycombinator.com/item?id=44941605)
	- HTML
		- SEO-friendly head links
		  collapsed:: true
			- ```html
			  <head>
			    <link rel="canonical" href="https://samplesite.com/page.html">
			    <link rel="sitemap" type="application/xml" href="https://samplesite.com/sitemap.xml">
			    <link rel="alternate" type="application/rss+xml" title="RSS" href="https://samplesite.com/rss.xml">
			    <link rel="search" type="application/opensearchdescription+xml" title="Search" href="https://samplesite.com/search.xml">
			  </head>
			  ```
			- The `canonical` link element tells search engines which URL is the **canonical version** of the page. This helps prevent duplicate content issues and ensures that the correct page is indexed.
			- The `sitemap` link element tells search engines where to find the **sitemap**
			  for the website. Sitemaps are XML files that contain a list of all the 
			  pages on the website and their metadata. They are used by search engines
			  to index the website and display it in search results.
			- The `alternate` link element tells search engines where to find the **RSS feed**
			  for the website. RSS feeds are XML files that contain a list of the 
			  most recent posts on the website. They are used by search engines to 
			  display the website's content in search results, as well as by RSS 
			  readers to display the website's content in a more convenient format.
			- The `search` link element is used by browsers to display a **search box**
			  in the browser's address bar. This allows users to search the website 
			  directly from the address bar, instead of having to navigate to the 
			  search page.
		- [HTML - Resource Preloading Cheat Sheet - 30 seconds of code](https://www.30secondsofcode.org/articles/s/resource-preloading-cheatsheet)