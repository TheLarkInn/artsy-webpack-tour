# artsy-webpack-tour
Annotations on webpack source code in a pseudo-guided fashion.

## Just an Experiment
My goal as one of the maintainers for [webpack](https://github.com/webpack/webpack) is being able to help developers better understand how webpack works. 

Demystify the tool so it helps you become more comfortable understanding how to use it and contributing to our source code and supporting packages.

## Have a question? 
The whole goal is to teach you how to use webpack, therefore please ask questions about the annotations you see inside of a github issue, and I will help you clarify any parts of what is seen below. There is **NO wrong question**. 

## Disclaimer: This may not match master!
I will likely not keep this up to date with every change in master on webpack/webpack. Rather, the purpose is to teach how to read and view the flow of the compilation lifecycle through webpack.

## Text Transcripts
To make this searchable, the text of each image has been transcribed into the "transcripts" section. The title of each transcript anchors to the respective image. The transcripts are not made to be read through (as they are useless without context), rather they provide a tool to search out a specific section based on the commentary.

### Help Wanted ❤😍💕❤😍💕❤😍💕❤😍💕❤😍

### Version (webpack 2.2.1+ from master)


<a name="Step1">![Step 1](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative01.png)</a>
<a name="Step2">![Step 2](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative02.png)</a>
<a name="Step3">![Step 3](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative03.png)</a>
<a name="Step4">![Step 4](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative04.png)</a>
<a name="Step5">![Step 5](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative05.png)</a>
<a name="Step6">![Step 6](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative06.png)</a>
<a name="Step7">![Step 7](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-compiler01.png)</a>
<a name="Step8">![Step 8](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-compiler02.png)</a>
<a name="Step9">![Step 9](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-compiler03.png)</a>
<a name="Step10">![Step 10](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-compiler04.png)</a>
<a name="Step11">![Step 11](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-compiler05.png)</a>
<a name="Step12">![Step 12](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-compiler06.png)</a>
<a name="Step13">![Step 13](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-compiler07.png)</a>
<a name="Step14">![Step 14](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-compiler08.png)</a>
<a name="Step15">![Step 15](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-compiler09.png)</a>
<a name="Step16">![Step 16](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf01.png)</a>
<a name="Step17">![Step 17](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf02.png)</a>
<a name="Step18">![Step 18](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf03.png)</a>
<a name="Step19">![Step 19](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf04.png)</a>
<a name="Step20">![Step 20](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf05.png)</a>
<a name="Step21">![Step 21](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf06.png)</a>
<a name="Step22">![Step 22](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf07.png)</a>
<a name="Step23">![Step 23](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf08.png)</a>
<a name="Step24">![Step 24](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf09.png)</a>
<a name="Step25">![Step 25](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf10.png)</a>
<a name="Step26">![Step 26](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf11.png)</a>
<a name="Step27">![Step 27](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf12.png)</a>
<a name="Step28">![Step 28](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-compilation-seal01.png)</a>

## Text Transcript

### [WebpackOptionsApply.js (List of plugins)](#Step1) 
"All plugins for options cases"
"These handle any module format"

### [WebpackOptionsApply.js (Explanation of Options)](#Step2) 
"getting opts from config"
"options target code"
"ES5 OOP (class W0A(?) extends 0A)"
"records"
"never used this before ¯\\_(ツ)_/¯ "
"plugin system makes for extremely flexible feature development"

### [WebpackOptionsApply.js (Native modules)](#Step3)
"Certain targets ship w/ other modules native to their deploy target like Electron"
"Similar to electron man but instead the "client" side. Thus diff externals"

### [WebpackOptionsApply.js (Source Map Flavors)](#Step4)
"handling bad target values"
"all of this logic is for the 'devtool' prop. Allows for about 15-20 flavors of source maps"
"That was Sean's first ever PR!!!"

### [WebpackOptionsApply.js (More module madness!)](#Step5)
"1. Single plugin for entry prop that is registered then"
"2. Executes via subsequent event"
"these plugins are grouped b/c they are all for module interop"
"these plugins all pertain to general optimizations including tree shaking"
"performance budgets code"
"in version 1, you had to do this yourself, now in v2 we handle it"

### [WebpackOptionsApply.js (after plugins)](#Step6)
"nice for custom plugins that need to execute after all other default plugins"
"same as abover except after resolvers are created"
"saftey net incase someone nulls the input fs"
"(Also resolvers are created here. The factory comes from webpack/enhanced-resolve)"

### [Compiler.js (The Complier's Constructor)](#Step7)
"The Compiler"
"yes, you can set your own custom file system"
"depreceate where the parser used to live"
"options from your config will end up here"
"Constructor"

### [Compiler.js (The Complier's Execution Process)](#Step8)
"top lvl. function for entire webpack compliation process"
"timings for builds"
"here are all of the compiler's plugin events"
"all plugin events start with 'applyPlugins'"
"that means you can write custom plugins for any of these events"
"still track time till the end"

### [Compiler.js (The Complier's Execution Process Part 2)](#Step9)
"next step in process (called inside of .run)"
"compilation is being created"
"create info to init compliation"
"the compilation plugins are firing"

### [Compiler.js (Compilation prelude)](#Step10)
"we drive into the compilation next"
"used for long term hashing"
"lets you plugin to multiple child compilations vs. just the parent"
"we create modules from here"

### [Compilation.js (Welcome to the compilation)](#Step11)
"plugin system"
"compiler thaty created it"
"Templates: bind the dep. graph to actual output code."
"the literal constructor for each dep."
"the shape of these templates vary by the type of dependency"

### [SingleEntryPlugin.js (Down the rabbit hole!)](#Step12)
"The plugins start to take over!!"
"theres one of those dep. types I was talking about"
"thats the values from your entry property"
"back to the compilation to start walking the dependency graph"

### [Compilation.js](#Step13)
"open empty slot for chunk about to be created"
"this is themodule that will be resolved"
"it wasn't originated from another module, so set null"
"next fn to visit :)"

### [Compilation.js (Building chains)](#Step14)
"track time to build chain"
"if 'bail:true', explode"
"else build anyways, show error after"
"safety net so deps are created properly"
"tip: depfactory.create = module"
"the dir path it came from"
"why an array? think nodes on a graph and dependencies are all adjacent nodes"
"a module is created: passed to callback!!"
"more timing"
"module officially added to compilation"
"Can also be null?"
"finish early if so"
"if a module is returned, use it and flag ready"
"I smell some recursion coming up!!!!"

### [NormalModuleFactory.js](#Step15)
"see if there is a cache entry first"
"allows plugins to hijack and modify original 'request' obj."
"IE: NormalReplacementPlugin"
"cache"
"return resolved module"

### [NormalModuleFactory.js](#Step16)
"this gets triggered from .creal"
"resolver event triggered & assigned"
"resolver is now going to ensure that the module you requested actually exists"
"don't error, skip"
"the result returned has everything needed to create module"
"will visit here next"
"more on this stuff later"
"the NormalModule instance is finally created"
"event for plugins to use"
"send module back to be added to chunk"

### [NormalModuleFactory.js](#Step17)
"as you can see callback handles resolved requests"
"find & extract loaders being used in require()"
"new code for handling ident in loader opts. "
"Rules are normalized from configuration"
"find all pre & post loaders"
"paths to loaders are now resolved"
"always ordered post-normal-pre"

### [NormalModule.js](#Step18)
"We are arriving here from the NormalModuleFactory"
"Parser instance"
"path the user specifies"
"path before query etc, are parsed"
"loaders to be applied"
"dependencies for context modules (superclass owns this.dependencies)"
"Normal Module constructor"
"extends module"

### [Compilation.js (Back to compilation!)](#Step19)
"just finished time for the callback"
"this new Normal Module"
"fails if factory fails "
"timing/profiling"
"check cache and profile"
"next stop"
"next stop+1"
"find deps of module to go through resolve, vreate, build process cycle till graph is complete"

### [Compilation.js](#Step20)
"Up until now, we know the following about our entry module: 
-request path
-loaders assigned and applied
-source value in new"
"we venture back to the callback"
"collect mod, and dep diagnostics, report the to compilation as errors"
"last chance for plugins to modify the NormalModule obj"
"Same as above for warning separately"
"Let plugins handle post build events"
"stable(?) topological ped sort. see compareLocations.j"

### [NormalModule.js](#Step21)
"timings"
"1. yet another callback 💕"
"Really important to remember that once inside this block, loaders have finally been applied"
"2. see if noParse is set if so, don't send to parser"
"3. pass raw src to parser along w/ options"
"4. if loaders are used correctly, the final loader will return js that acorn can parse, else FAIL! "

### [NormalModule.js](#Step22)
"still here"
"a value ref. later for Loaders."
"1. What is loaderContext? The loader contect rep. is also known as the Loader API. It is a collection of utilities and stateful info about the current module being loaded"
"1a. loader context"
"Finally!! Loaders are ran!!"
"2. This fin actually comes from a  supporting npm module: loader-runner."
"loaders can specify deps of their own declaratively" 
"like css => background img"
"css-loader => url loader"
"2a. loader runner"
"3. can also return a buffer"
"4. if supported loader sends back src maps."
"5. remember last sketch? we send back to be parsed"

### [Compilation.js](#Step23)
"We've already covered this tl;dr caching"
"finally back 2 levels up of callbacks"
"?=unresolved"
"oh hey no context switching <3"
"timing & profile"
"the next step in building the dep graph"
"right now at this point we only have 1 module"


### [Compilation.js](#Step24)
"for now, lets consider this the entry module."
"the final call from addEntry fn"
"unflatten deps"
"deps. can come from some 'resourece' aka file/resolved location, this dedupes the loc. and groups by [[dep1, dep2],...[block],...]"
"hard to explain; 100% a module is a dep block dep block is hisgest super class that exists to rep. dep. relationships"
"time to add all deps & bfs graph traversal"
"OMG I JUST Figureed out DependenciesBlock fully just now!!!"
"So the whole point is that deps can be uniq bit from the same place"

### [Compilation.js](#Step25)
"profiling"
"since we've gone to a signle entry dep to now an arrau pf deps we'll need to iterate through them"
"i can haz functional error handling?"
"by calling create"
"now we async iterate through all deps and process them w/ their dep factory"
"warnings & error handlers"
"Already learned this fun stuff"
"tie deps back to origin modules (2 way ref.)"
"profile pt1"
"end of 1 way traversal"
"cache checks"

### [Compilation.js](#Step26)
"some profiling + ?"
"recursion begins"
"remember we are still inside async factory iterator also."
"recurse the graph!"
"we can actually go back to original event"
"finally traversal is complete"

### [Compiler.js](#Step27)
"Brain Recapitulation!!!!"
"We just spent like 5 hours in Compilation, but the graph is done building and now we are back"
"this is where we last left off"
"finish & seal are next to be called..."

### [Compilation.js](#Step28)
"lets dive in to here"
"warnings & errors"
"triggered here yay!"