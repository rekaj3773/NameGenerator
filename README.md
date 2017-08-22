# NameGenerator
Creates quick 3-5 character random name based loosely on English consonant and vowel rules

See it in action: .io page coming soon.

###### Some names this might generate:

- Moj 
- Lirza 
- Heqan 
- Jut 
- Ureg
- Gic
- Ekva
- Pogli

NameGenerator uses Regular Expressions to create names by randomly selecting a regular expression using randexp.js that falls within English naming rules.

##### The loosely based English Rules *(or quasi rules as I call them)*.
If you know regular expressions, you can jump right in and read them through a RegEx. Todo: jump to Regular expression below.

All names must be at least 3 characters in Length.  Two letters or less are less common and may be less meaningful.  (If you'd like a two character name, just take the first two of any generation)

**Starting with a vowel:**

All names starting with a vowel (V)[V], must be followed by a consonant (C)[VC].
Afterwards, all names starting with a vowel can have the pattern [VCCVC], [VCVCV], or [VCVCC]

**Starting with a consonant:**

Alternatively, starting with a consonant (C)[C], you must be followed by a vowel (V)[CV] *(except in cases like Kh or Sl, but maybe we incorporate those later)*.  Making branching even easier, this combination is only reasonable to then add another consonant in the third character's place [CVC] since we don't often see two vowels together in names *(excluding ae, ye etc)*.

All names starting with a consonant can have the pattern [CVCVC] or [CVCCV]

**Putting it all together**, all combinations derive from a 3-5 characater subset of the following [VCCVC], [VCVCV], [VCVCC], [CVCVC] or [CVCCV].

##### Example: 
For ease of example, let's assume all consonants are "T"s and all vowels are "A"s.  
The below names all seem plausible.

E.g. Tatta, Atta, Tata
However, the next names do not seem so plausible.
E.g. Aaa, Tta, Tataa

Replacing those T's and A's, you can see the regular expression below.

```regex
[aeiouy][bcdfghjklmnpqrstvwxz]([bcdfghjklmnpqrstvwxz]([aeiouy][bcdfghjklmnpqrstvwxz]?)?|[aeiouy]([bcdfghjklmnpqrstvwxz]([bcdfghjklmnpqrstvwxz]|[aeiouy])?)?)|[bcdfghjklmnpqrstvwxz][aeiouy][bcdfghjklmnpqrstvwxz]([aeiouy]([bcdfghjklmnpqrstvwxz])?|[bcdfghjklmnpqrstvwxz]([aeiouy])?)?)
```

Don't remember how to use Regular Expressions *(like me always forgetting)*, check out one of the quick guides.  Guides like [regexone](https://regexone.com/) are great.  Check out [zeeshanu](https://github.com/zeeshanu)'s [Learning Regex the Easy Way](https://github.com/zeeshanu/learn-regex).


Prefer to see it broken out visually, check it out on [Regulex](https://jex.im/regulex/?#!embed=false&flags=&re=(%5Baeiouy%5D%5Bbcdfghjklmnpqrstvwxz%5D(%5Bbcdfghjklmnpqrstvwxz%5D(%5Baeiouy%5D%5Bbcdfghjklmnpqrstvwxz%5D%3F)%3F%7C%5Baeiouy%5D(%5Bbcdfghjklmnpqrstvwxz%5D(%5Bbcdfghjklmnpqrstvwxz%5D%7C%5Baeiouy%5D)%3F)%3F)%7C%5Bbcdfghjklmnpqrstvwxz%5D%5Baeiouy%5D%5Bbcdfghjklmnpqrstvwxz%5D(%5Baeiouy%5D(%5Bbcdfghjklmnpqrstvwxz%5D)%3F%7C%5Bbcdfghjklmnpqrstvwxz%5D(%5Baeiouy%5D)%3F)%3F)) *(I love this tool.)*
![alt text](https://github.com/rekaj3773/NameGenerator/blob/master/regulex.png "Image of the RegEx from Regulex.com")




**Full disclosure**: This is my first Github project!:smile:  I would greatly appreciate if you'd help me learn and offer advice where able.

This project started a long time ago thanks to inspiration from [Bill Best](https://github.com/wmbest2), Android Guru and all around smart guy.  Why not use this as my start to learn Github.

The original version showed how weak of a programmer I was.  It was written in Java, had ugly if statements and used cases in cringeworthy fashion.  Want to see it?  (To come) Somedays I still feel I do things just as silly. 

## Table of Contents: 
To come

## Installation: 
To install locally, you need to reference [randexp.min.js](https://github.com/fent/randexp.js) created by [fent](https://github.com/fent). 

Fent created a JavaScript that will "Create random strings that match a given regular expression".  He even wrote a [great page](https://fent.github.io/randexp.js/) on how to use it. 

Installation gif:
To come

## Usage: 
``` javascript
txt = new RandExp(/([aeiouy][bcdfghjklmnpqrstvwxz]([bcdfghjklmnpqrstvwxz]([aeiouy][bcdfghjklmnpqrstvwxz]?)?|[aeiouy]([bcdfghjklmnpqrstvwxz]([bcdfghjklmnpqrstvwxz]|[aeiouy])?)?)|[bcdfghjklmnpqrstvwxz][aeiouy][bcdfghjklmnpqrstvwxz]([aeiouy]([bcdfghjklmnpqrstvwxz])?|[bcdfghjklmnpqrstvwxz]([aeiouy])?)?)/).gen();
```


In a quick html page example: 
```html
<html>
<button id="btn">Generate</button>
<p id="para" ></p>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
<script src="randexp.min.js"></script>
<script>
	$(document).ready(function () {
	
	var txt="";
	$("#btn").click(function(){
		txt = new RandExp(/([aeiouy][bcdfghjklmnpqrstvwxz]([bcdfghjklmnpqrstvwxz]([aeiouy][bcdfghjklmnpqrstvwxz]?)?|[aeiouy]([bcdfghjklmnpqrstvwxz]([bcdfghjklmnpqrstvwxz]|[aeiouy])?)?)|[bcdfghjklmnpqrstvwxz][aeiouy][bcdfghjklmnpqrstvwxz]([aeiouy]([bcdfghjklmnpqrstvwxz])?|[bcdfghjklmnpqrstvwxz]([aeiouy])?)?)/).gen();
		$("#para").text(txt);
	})
	});
</script>
</html>
```

## Credits: 
To come

## License: 
This is under MITs license.  Please use this however you'd like as long as you attribute me and don't hold me liable!
