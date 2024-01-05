                                             

# Namaste react

lecture 2
1) what changes do we need to make our app productionn ready?
 - we have to optimize it 
 - remove console logs
 - servers
 - we need to minify our files
--> to use all these functionalities we need bundlers<br>

2) Job of bundlers
def:- bundler is a tool that takes all the separate pieces of code and assets that make up a web appication and combines them into a single , optimize package.<br>
 this package typically includes js files, stylesheet, images and other assets.
ex:- webpack (it is for production tready apps)
   - vite
   - parcel

-> bundlers like parcel, webpack  and vite are nothoing but packages with js code that helps us to bundle our code files and and assets that are required for production ready app.<br>

-> to install parcel (a package)  we need a pacakage manager --> npm (node package manager)

-> Ex:- npm (node package manager)-> default package manager for node.js and js  
        yarn - alternate package manager for js
        pip 
        conda


3) why we need npm ?<br>
-> it manages ppackages in our app<br>
-> our app didn't only run on react<br>
-> it requires a lot of packages to make it functioning.<br>
-> so we need to download lots of packages <br>
-> so npm helps us to download and manage those packages<br>

3.1) How to initilize npm<br>

-> npm init
-> npm init -y
-> npm install -D parcel

4) commands to install pacel package<br>
-> npm install -D parcel       --> -D show for dev dependency. we are not installing it for production instead we want parcel only on our machine.<br>
-> npm install --save-dev parcel     --> both are same things<br>

5) dependency <br>
-> it means the packages our project depend on.<br>
->there are different types of dependencies (1) dependencies (2) devdependencies<br>
-> dev-dependencies is limited to development side <br>
-> and dependencies are use globally like react.<br>

6) caret (^) and tilde (~) in package.json<br>
-> it is use befor the version of dependencies<br>
-> if we want the modify if minor version changes then use (^)<br>
-> if we want to modify the major version the use          (~)<br>
-> don't use anything if we don't want to upgrade <br>

7) package-lock.json<br>
-> it locks the version of package that yuo use <br>
-> it is the proof that we are using specific versions. <br>
-> it lock the versions of denpendencies<br>
-> it should be out of gitignore.<br>
-> it mantain the hash of the version---> it maintain the integrity.<br>
-> 

8) node modules folder in our app<br>
-> whenever we install packages from npm its node module package comes<br>
-> it is like database of our nmp.<br>
-> it has all the sub packages / dependencies that out parcel will require<br>


Note👉👉: <br>
<p>
aapalyala app create/ run karayla kahi packages lagnaar aahet (like parcel) --> te nanter dependencies madhe mojle jatat. kadhi kadhi asa hote ki tya dependencies la pan dusrya dependencies ver nirbhar rahav lagte. ter tya sarva dependencies chi info aapalya package-lock.jsom madhe dili aste. aani tyachya related packages node modules store kele astat. package-lock.jsom madhe enough information dili aste ki te purna node module ch folder create karu shakte 
</p>



Note2👉👉<br>
: we should not add node modules to our gitignore because it is too heavy. <br> 

Node3👉👉<br>
: the question arises here is then if we push our app to github or on server and you said ki we need not to push node module folders to it then <br>how can our app will work?<br>
--> the ans is our package-lock.json --> it is responsible to regenerate whole node package module on web itself. <br>
-> we need not to push node modules folders to git and further package-lock.json will create itself.<br>


9) Install react using npm<br>

-> look the seen is two ways we can install/attach react our project <br>
     -> by using cdn links 
             --> one for react 
             --> one for react-DOM
-> but usign cdn is slight time consuming way. <br>
-> instead that we can have all the react forlders and dependencies at our own server in form of node packages<br>
-> so better way is to install react packages at our machine usi<br>ng npm
-> npm will store react dependency in jackage.json<br>
   and and its information in package-lock.json and<br>
   its modules store in node modules package.<br>

npm commands:<br>
-> npm install react     -> download react packages<br>
-> npm install react-dom -> -"-  react-dom packages<br>

NOde👉👉:<br>
 we wants react globally so that's wht we are not using "(-D)" here.<br>


10) igniting our react app<br>
command:-> npx parcel index.html<br>
-> npx ---> it means execute using npm<br>
-> entery point --> index.html <br>

11) Functions of Parcel / How our react App works and how all things goes behind the seen<br>
-> when we ignite our react app tgere is lot mantyy things are working together to make our react app run!<br>
In background we have<br>
-> dev-dependencies<br>
-> dependencies<br>
-> node modules<br>
-> parcel and many more.<br>

all of then work together in cordination to run react app<br>

👉 HMR - hot module reload -> whenever we save our code file in vsc we can see the change in app as sson as we save code files. this is done with the help of HMR which is present in parcel.<br>
👉 File watcher Algorithm --> written in c++ --> is continuously watching/monitoring files and if any change happens it reflects it instantly.<br>
👉 Bundling --> done by parcel<br>
👉 cleaning our code  --> done by parcel
👉 dev and production build  
(these are the two types of building our app with parcel. dev build require less time as compaired to production builds. the seen is everything is dependent on files and minification of files done by parcel.)<br>
👉 super fast build algorithm<br>
👉 image optimzation. --> images / media take the larges time to reload. Parcel is so pwerful that it optimize images / media also.<br>
👉 caching while developing. --> it is an important concept while dveloping / building our react app. When we build our app using parcel for the first tieme it take more time as compaired when we build it subsequent times. this is beacuse first time parcel have to go through all files which is time consuming. to prevent that parcel create its own folder to save the caching data. using that data parcel can build the next react app in less time. <br>👉this is the concept.
👉compression:-><br>
👉Compatible with older version of browser<br>
👉HTTPS on dev<br>
👉port number<br>
👉consistent hashing algorithms<br>
👉zero configuration<br>


12) Transitive dependencies? what are they ?<br>
👉react app is so fast<br>
-> to make that app fast it requires numbers of dependencies
-> that dependencies may depend on another dependencies<br>
-> the the chain goes on <br>
-> this dependency chaining is called as transitive dependencies<br>


13) What is a browserslist<br>
👉 It is is the dependency in package.json <br>
-> it specifies the the version and the type of browser our code must work.<br>
-> if we are specifying specifying any specific version and browser name it wont' mean that it will only work in that browser and do not work in <br>other. it will work in other browsers but some function will not work.<br>

14) what is a polyfill<br>
👉 this concept is related to the code compatibility of older browsers<br>
-> some our app code won't work in older browsers.<br>
-> so to make our app run in older version of browsers we use babel created some code with similar functionality to the code which browser do not support<br>
-> the converted code is called ⭐Polyfill⭐<br>
-> babel do automatically for us<br>

15) What is Tree Shaking <br>
👉 it means ⭐Removing unwanted code⭐<br>
-> parcel removes the unwanted code that libraries bring with them and uses only the important one.<br>


16) what is npx<br>
👉 npx = execute the commmand without downloading the package;
-> npx = npm run<br<br>>
-> npx parcel index.html   -> command to run app<br>
-> npm run parcel index.html -> we can use it instead npx<br<br>>

😂Easy way to run out app<br>
-> we can directly run out script from package.json'<br>
-> we can add commands inside script that can use ulternative to npx command <br>
-> inside scripts:{ "start":"parcel index.html"<br>
"build": "parcel build Index.html"}<br>
-> now we can use command like ⭐npm run start / npm start and npm run build / npm build⭐<br>

17) How can we remove console logs from project<br>
-> parcel do not remove console logs by itself<br>
-> we have to add babel plugin and the configure it <br>
to remove console logs<br>
-> for that we have to go to *babel-plugin-transform-remove-console*<br>
-> and then isatall the package using *npm install babel-plugin-transform-remove-console --save-dev / -D* command to install the package<br>
-> we can see it inside node modules and package-lock.json<br>
-> next step is to configure that plugin by creating the .babelrc file and add the specification there from the website.<br>
-> .babelrc is configuration file for babel plugins<br>

=======================================================================================================

# <br>Lecture 3<br>
(core concepts of react #babel, #jsx, #many-more)

👉untill now we were using React.createElement("tag_name", {key}, "innerHTML").<br>
-> And the motive of react was to write html using js but in easy way.<br>
-> But always using React.createElement() for creating html tags was so ugly.<br>
-> this is even worst when we need to creted multiple tags inside a single tag.<br>
😍 So to tackle this facebook developer develop JSX<br>

1) what is JSX<br>
👉 JSX is HTML like Syntax use to create html element in js code.<br>
-> jsx is not HTML inside JS<br>
-> but it is HTML like syntax inside js<br>
-> there are slight differences in syntax
<br>
H.W<br>
-> how to create img tag inside html
-> 

2) Howdoes React.createElement() executed  ?<br>
👉 React.createElement() -> return a object<br>
-> that object is then rendered on virtual dom using ReactDOM.render(object, location);<br>
-> React.createElement() ==> object ==> render on HTML DOM ==> js engine creates execution context ==> renders on webpage<br>

3) How JSX works ?<br>
👉 our browser do not understand JSX<br>
-> browsers acn only understand javascript<br>
-> babel is the one which helps to execute JSX<br>
-> babel is compile for modern javascript<br>
-> behind the seen babel converts the JSX code and executes it<br>
-> babel uses React.createElement() to create new elements.<br>
-> inshort execution of JSX works like this<br>
⭐JSX ==> React.createElement() => object ==> HTML dom⭐<br> 

🏅🏆 JSX is so powerfull<br>
-> it do js code sanitijation<br>
-> means it only use the secure code comming in form of js<br>
-> it made easy to write react elemet inside functioanl component<br>
-> it also can write another funct. component to current functional component<br>

4) Components in React<br>
⭐Functional components<br>
⭐Class base components<br>

⭐Functional components <br>
-> They are normal function expression who have JSX inside them<br>
-> there are many methods to execute them<br>
-> functional components can be created using an arrow function and JSX written inside them<br>
-> we have write JSX code inside * (); *<br>
-> render method only renders the react element and JSX<br>
-> if we wants to render our functional component which is nothing but the function expression having JSX inside we have ro write it in JSX syntax <br>--> *<function_comp_name/>*<br>

🔥how to write react element inside finctional component<br>
-> use *{.....}*  to mention the react elemet<br>

🔥how to write another functional component inside other functional component<br>
-> use jsx syntax *<..../>* <br>


summary:
1) add script for running app without npx<br>
2) add script for build<br>
3) add browserlist and its description<br>
4) install plugin<br>
5) how to configure babelrc<br>
5) keys in react element / props<br>
6) JSX<br>
7) react element using jsx<br>
8) components <br>
9) its syntax / styles<br>
10) how to use react eelemnt inside component<br>
11) how to render component<br>


===========================================================================================================================================

# Lecture 5

1) <h3>Components</h3>  
-> there are 2 types<br>
-> functional and class base components<br>
-> first letter should be capital 
-> use <Component_name/><br>
-> we can have only one element inside the component<br>
-> to use multiple components use it inside React Fragments<br>
-> we can use any type of javascript inside component using {} brackets<br>
-> react can render only one root element so make one parent component<br>
-> we can create multiple child elements using component and use it inside the parent <br>


2) <h3>Inline CSS</h3>
-> like in HTML who we use inline CSS we can use it here</br>
-> only difference is we have to use {} after style.  like style={{backgroundColor:"yellow",}}</br>
-> we have to write css properties like objects in JS</br>
-> properties name are also different while we use Inline css</br>
-> normal (background-color:black)    ---> in jsx/component/ react   (backgroundCOlour:"black")</br>
-> only difference is write words in camel casing type and write it who we write objects</br>

3) <h3>React Fragments</h3>
-> Inside components we can only have one parent element<br>
-> therefore we have to use unnecessary div to insure there will always be one parent element<br>
-> to avoid that react provides fragments<br>
-> we have to put our child elements inside it and now it will behave like one parent element<br>
-> syntax <React.Fragments></React.Fragments>   / <></><br>


4) <h3>Components Writting Journey</h3>
-> created a restaurant card components and simply use it multiple times in body<br>
-> then created the restaurand object which takes card details <br>
-> then instead of static typing the data of restaurant inside card i am using restaurant object data inside it <br>
-> the plan is to fetch lots of objects from api and then render them inside body by fetching each restaurant data.<br>

5) <h3>DIfferent ways of passing Props</h3><br>
-> we learnt 4 different way we can pass props<br>
-> inshort if we want to pass the data of any individual object we send it in form of props<br>
-> we can use any name like props as argument<br>
-> if we have multiple things to pass as props we can use {...} --> spread operator to do that<br>
-> 


<!-- ============================================================================================================= -->

# Lecture 6

what should we put into config.js file and why do we need config file <br>

1) Config File /constants file <br>
-> we should put all the hardcoded things in congig.js file <br>
-> We should name export each and every element from confign<br>
-> This is because we might config file contains different static data<br> 
-> we might need specific data from there<br>
-> thats's why we need to export each element by their name<br>

2) What are hooks<br>
-> hooks are normal js functions<br>
-> they came with certain functionality <br>
-> they are use to create local state  variable<br>

3) How input works in react<br>
-> input works differently in HTML and React.<br>
-> In React there is one way data binding<br>
-> we cannot write directly inside input element in react <br>
-> one way is we can create a const variable in js and assign it as a value to input<br>
-> but still it will be static <br>
-> To make input working in react we have to do data binding through state variable<br>
-> ans state variable is created using useState()<br>



4) what is useState()<br>
-> import as name import --> {}<br>
-> use to create local state variables<br>
-> useState() returns a array <br>
-> the 1st element of that array is variable name <br>
-> main thing is we cannot directly change the state of this variable<br>    --> using onChange(e.target.value)  ❌❌<br>
-> usestate provide us a function to change the state of local sgtate variable through it.<br>
-> whatever we write then will update in the local variable. <br>
-> i.e setLocalVariableName<br>
```javascript
   const [searchInput,setSearchInput] = useState("KFC");
   onChange =
   {(e)=>
      {
         // e.target.value;
         setSearchInput(e.target.value)

      }
   }

```
>![NOTE]
> we can also write e.target.value without setSearchInput but this is not the write way <br>
> now we can use searchInput as our local variable and we can use it anywhere in code <br>
> This is called 2-way data binding<br>
> 2-way because we are reading and writting the adata at the same time.
<br>
> we can change the local state veriable using onChange() method<br>
> and in react onChange() we have to put arrow function and uit automatically get the event property. (e)<br>
> using that event property we can read whatever we are typing <br>
> if we are able to read we can update it using (setSearchText(e.target.value)<br>
)
### How to create vriable in JS and React <br>
```
const vstext = "hello"  // by default this variable is hello---> tjis is in javascript

conat [searchText,setSearchText] = useState("hello")  // here by default hello is assign to react variable 

```

5) why do we need state Variables<br>
-> if some other components change our local varibales <br>
-> react cannot tract the normal local variables<br>
-> if there is any change in local variables react my not know it and that variable may not render on UI properly<br>
-> **If we want our variables is in sync with UI we need to use State variables**<br>


6) How to create a True / false toggle button using state variable<br>
-> create a state variable with default value false<br>
-> write a arrow function inside search button on Onclick event <br>
-> and update the setVariableName() <br>

```
```javascript
   const [displayBoolean, setDisplayBoolean]  = useState("false");
   <button className="search-btn" onClick={()=>{
              if(displayBoolean==="False")
              {
                setDisplayBoolean("True");
              }
              else
              {
                setDisplayBoolean("False");
              }
            }}>Search 
   </button>

```

7) Code / workflow of searching and element through Search bar<br>
-> Created the state variable for storing search text --> and use useState()<br>
-> onChangeing state of search box set to state variable using setVariable_Name <br>
-> Create another state variable for restaurants <br>
-> create a filter function which will take searched data inform of statevariable and return related object <br>
-> finally set the data return by the filter function to render its elements<br>


<!-- ========================================================================================================================================================== -->


# Lecture 7

1) What is Config / config driven UI<br>
-> config is nothing but the JSON object<br>
-> like one we reated inside our project<br>
-> like we store data inside it for using it globally <br>
-> similarly backend send configs for perticular sections like crowsels and normal UI <br>
_> so inshort whole UI can be manage by COnfig <br>
-> such UI are konwn as config driven UI<br>
-> COnfig is no thing but the JSON Object <br>

2) topics covered in this lecture<br>
-> useEffect() hook <br>
-> we use optional chaining <br>
-> we maintain 2 separate state variables for storing all restaurants and filter resataurants<br>
-> we use Shimmer UI<br>
-> using of useEffect() hook / why do we need this hook <br>
-> calling api and using async await and using it inside useEffect() hook <br>
-> we do conditional rtenderinng<br>
-> we learn molithic and micro services architechture<br>
-> we are building only one microservice and that is  UI <br>
-> 2 way t load / render our page <br>
 - loading page = load API -> then render page<br>
 - loading page = render first -> API call() after <-- this one is preffered and here when our useEffect() usecase emmerge <br>
 -> learn about CORS / their functionalities / they use to trick the brousers to make the API call from our local machine 

3) useEffect() hook
-> it is a hook 
-> it takes 2 arguments
-> 1st argument is a callback function --> mostly a callback function with API call
-> 2nd parameter is a dependency array 
-> if the array is empty useEffect() will call only once after the initial render
-> if we pass elements/object to array 
-> based on those objects of dependency useEffect() will be called.
-> suppose we have a state variable inside out dependency array -> useEffect will be called whenever there is state change in state variable  
> sequesnce ==>  components will render -> useEffect will be called --> it will called again after change in state of stste variable 

```javascript

//  when we do not pass any dependency array it will call once after every render  // here in this case useEffect() default behaviour will be called which is called after each render
  useEffect(()=>{});

// same case as dependency array is empty --> that means no dependency --> it will be called only once after ibitial render and not for other frequent renders
  useEffect(()=>{},[]);

// it will render after search text local state variable state changes
  useEffect(()=>{},[searchText]);

  async function getRestaurants()
  {
    const data = await fetch("");
    const json = await data.json();

    setRestaurants(json?.data?.cards[2]?.data?.cards);
    setFilterRestaurants(json?.data?.cards[2]?.data?.data?.cards);
  }


```

<!-- =============================================================================================================================================  -->

# lecture 8

Note👉:
> never create a component inside a compoenent it will create a render problem 
> never create a state variable [ useState()] inside if else and for loop
> never create a state variable outside your functional componenrt -> always create it inside the bofy of functional components
> we can create more than one useEffect();


1) React routers
-> just install using npm install react-router-dom
```javascript
 npm install react-router-dom   // install react router package from npm

```
-> react routers are use to create routes --> that means navigate to certain place/page
-> to use react router we have to first configutre then and then render it instead of main app layout
-> first named inport "createBrowserrouter" --> this is a function that is used to create the configuration
 -> it takes array 
 -> the array has the list of route configuration and error messages

```javascript
 import { createBrowserRouter } from "react-router-dom"

 const appRouter = createBrowserRouter([
   {
      path:"/",
      element:<AppLayout>,
   },
   {
      path:"/About",
      element:<About />
   }
 ])
```
👉
> Now we need to render according to this configuration
> that's why we need to provide this confi. to render
> for that we use RouterProvider

-> second we have to named import the routerProvider
 -> it is basically component
 -> we use routerProvider to render instead of AppLayout component
```javascript
import {RouterProuder} from "react-router-dom"
root.render(<RouterProvider router={appRouter}/> )  // we have just provided the configuration created using createBrowserRouter to RouterProvider as props
```


2) Types of routing 
-> client side routing 
-> server side routing

3) how to empliment client side routing what are its uses
-> we use <link to="/target">Target</link> tag to route inside the page
-> when we want to route multiple child components we have to use <outlet/> tag 

```javascript
const AppLayout = ()=>
{
   return ( 
      <Header/>
      <Outlet/>  // <--------this is outlet
      <Footer/>
   )
}

const appRouter = createBrowserRouter([
   {
      path:"/",
      element:<AppLayout/>,
      errorElement:<Error/>,
      children:[
         {
            path:"/",
            element:<Body/>
         },
         {
            path:"/about",
            element:<About/>
         }
         {
            path:"/Contact",
            element:<Contact/>
         }
      ]
   }
])
```

4) What we lernt in this lecture
> we can create multiple useEffect()
> we cannot write useState() inside if else
> we can have can import images from our machine -> using assets folder  -> it is export as defult export by default.
> how can we use our own shimmer instead of importing package from npm
> learnt about formik for form --> goto tutorial 
> implement routers using createBrowserRouter() --> takest an array of list of configuration/object of routes.   we can have children inside. we provide it in <outlet/>
> RouterProvider is the component use to render instead of  AppLayout
```javascript
root.render(<RouterProvider router ={appRouter}>)    //appRouter --> this is the variable which stores all the configuration of createBrowserRouter.
```
> we have done dynamic router using {useParas} from react "react-router-dom"
>note:-> always use optional chaining
> we learn to use link component  //  <link to=""></link>

<!-- ============================================================================================================ -->

# Lecture 10 (Class base components)

1) React lifecycle --> an inportant concept for class based conponents  
> React lifecycle:->  mounting ----> updating ---> unmounting
2) 2 phase in react -> render phase and commit phase
3) useSatet() -> in functional       this.setSate() --> in class based comp.
4) useEffect() -> in functional      componentDidMount() -> in class based comp.
5) if we do not have props / states then there will be no update in lifecycle --> only mounting and unmounting
6) componentWillUnmount is use to clear the mounting of component


<!-- ============================================================================================================== -->

# Lecture 11  (optimizing our app)

1) lazt loading

2) code splitting 

3) building our own hooks 

4) when / how / why  should we build hooks
> reusability
> readability
> separation of consern

5) Create utils folder to save utility functions 
> make our more modular  
> this makes our code for testable 
> readable 
> makes code maintainable 
> easy to debug 

6) what ever the extra code instead of components we can write then as hooks--> this is the time to create our custom hooks
> whenever we see the messy code we can wrap up it outside of component
> this done using hooks
> hook are js arrow function returning the values.

7) we have created new feature called isOnline/isOffline using custom hook
> create useOnline hook 
> then export deafalt it to make use of its working.
```javascript
const useOnline = ()=>{
   const[isOnline, setIsOnline]=useState(true);
   useEffect(()=>{
      window.addEventListener("online",()=>{ setIsOnline(true);});
      window.addEventListener("offline",()=>{ setIsOnline(false);});
      return isOnline;
   },[]);
   
}

export default useOnline;
```

>![Note] 🔥 
> whenever we use addevent listener we need to remove it else it will be called for every time new render occures
> in above code we have use addeventlistener 
> once we have set the values of "isOnline" variable we must remove the event listener
> below is the code to remove the event listeners once we set "isOnline"
> create hook for authentication / etc,
```javascript
const useOnline = ()=>{
   const[isOnline, setIsOnline]=useState(true);
   useEffect(()=>{

      const handleOnline = ()=>{ setIsOnline(true);}
      const handleOffline = ()=>{ setIsOnline(true);}

      window.addEventListener("online",handleOnline);
      window.addEventListener("offline",handleOffline);
      
      return ()=>{
         window.removeEventListener("online", handleOnline);
         window.removeEventListener("offline", handleOffline);
      }
   },[]);
   
   return isOnline;
}

export default useOnline;
```

8) Dynamic Bundeling Concept

>![Note]
> we use parcel as a bundler which bundle all the code into one js file.
> That js file contain all the js code we have written in our project
> when out app is huge is became inefficient to load that js file --> it contains all the code 
> at that time we use the concept called dynamic loading / code splitting
> there what happen is instead of normal importing the components we just import them dynamically 
> so that the specific component will only loads when we use it in actual app

-> dynamic bundelling can be called as
 - CHunking
 - Code splitting
 - Dynamic Bundling
 - lazy loading
 - On demand Loading 
 - Dynamic import 

```javascript 
const Instamart = lazy(() => import("./components/Instamart"));
```
-> react provide function called lazy() which is named import from react which provide the capbility to do dynamic loading.
-> upon on deman loading -> react load that secific components/file dynamically first.
-> for the first time it gives error because it takes time to load that daynamic content.
-> second time you visit that perticular component/file it will load properly

>[!Note]
> to make this process smooth 
> react provide a component called <Suspense></Suspense>
```javascript
import {lazy, Suspense } from 'react'

<Suspense>Instmart</Suspense>
```
> spspense tage will understand that we have dynamically loaded some content.
> it provide one prop called "fallback"
> "fallback" is use for showing shimmer like components untill content in suspense loads properly.
> we should not lazy load inside components else we have to lazy load at top after all the imports done.

```javascript
<Suspense  fallback={<Shimmer/>}>Instmart</Suspense>
```


# Lecture 12

1) Different methods to write css
-> Normal CSS
-> inline css
-> using SCSS / SASS
-> Using component Libraries
 - Material UI
 - Ant UI
 - Base UI
 - Chakra UI
 - Styled COmponents  
-> using Frameworks
2) pros
-> development process becames fast
3) cons
-> it increase the bundle size
-> forced UI

>![Note]
> While going for interviews whe should know about the pros and cons of using different css methods we can use to style our ptoject.

4) TailWind CSS
-> it will remove the default css
-> It will override css
-> It provide classes to add style in our html
> import the script of tailwind from official website
> init tailwind and post css
> we will get the dev-dependencies of tailwind and postcss
>we will get the tailwind.config.js
 - we have to configuration of tailwindcss
 - in content:["./src/**/*.{html,js}",]

```javascript
//how to install taildwind css and postcss pa ckage 
npm install -D tailwindcss postcss

//initialize tailwindcss
npx tailwind init
```

5) what is postcss
-> while using tailwind css we need to work with classes
-> postcss is the package which will tell bable that those are the classes of tailwindcss compile them to normal css.
-> like bablerc files we have to create the .postcssrc file
-> we have to store some configuration here 

6) Code inside our css will only have 3 line that tailwind provides us.

