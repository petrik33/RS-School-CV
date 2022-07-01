# Timofey Petrikevich

## Contact Information

- Email: petrik3003@gmail.com
- Discord: petrik33#0076
- Telegram: @IamAnAlligator
- Phone: +375-29-199-04-88

## About Me

![My photo(very attractive boy)](<./Images/photo_2022-06-29_13-48-43%20(2).jpg>)

I am currently a first-course student of Belarusian State Univerity's Faculty of Applied Maths and Computer Science. The spheres of my interest in the world of IT are:

- Front-End Web Development
- Mobile Software
- Game Design/Programming

I started self-studying [GameMaker](https://gamemaker.io/ru/gamemaker) as my first game engine and after a year of solo work found a partner to collaborate with - young brazilian artist [Kure Mothri](https://linktr.ee/kuremothri). Together we started making a game, which is still in progress - Sunset Forest. ![Start Menu Screenshot](<./Images/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%20(598).png>)
I am really keen on working in a team of trusted people after my experience with Thirty Three Infinities Studio - this is how we called ourselves after adding sound designer and composer to us.
My current goals are to learn how to develop mobile apps using React Native and games using Unity and C# language.

## Skills

- GameMaker Engine
- C++ language and OOP model
- Game Programming Design Patterns
- VCS Git (remote service GitHub)
- QT Framework
- HTML + CSS basics
- GLSL basics (in 2D)

## Code Examples

Here is a fragment shader code responsive for my day and night dynamic transition in the Sunset Forest game. Although it is done mostly by following online tutorial I had to make some changes to adopt it to our own game. Also it requires working with color values and in-game light objects.

```
varying vec2 v_vTexcoord;
varying vec4 v_vColour;

uniform vec3 col;
uniform float con_sat_brt[5];

uniform sampler2D lights;

#define contrast con_sat_brt[0]
#define saturation con_sat_brt[1]
#define brightness con_sat_brt[2]
#define pop_strength con_sat_brt[3]
#define pop_threshold con_sat_brt[4]

void main()
{
	vec3 base_col = texture2D( gm_BaseTexture, v_vTexcoord).rgb;

	float grey = dot(base_col,vec3(0.299,0.587,0.114));

	//overlay
	vec3 out_col = grey > 0.5 ? 1.0 - (1.0 - 2.0 * (base_col - 0.5)) * (1.0 - col) : 2.0 * base_col * col;

	//add saturation
	out_col = mix(vec3(grey),out_col,saturation);

	//add contrast
	out_col = (out_col - 0.5) * contrast + 0.5;

	//pop lights
	out_col = out_col + pop_strength * max(grey - pop_threshold,0.0);

	//add brightness
	out_col = out_col + brightness;

	//handle lights
	vec3 lights_col = texture2D(lights, v_vTexcoord).rgb;
	grey = dot(lights_col,vec3(0.333));
	out_col = mix(out_col, base_col * normalize(lights_col + 0.05) * 3.0, grey);

	out_col += 0.1 * lights_col; //Optional

    gl_FragColor = vec4(out_col,1.0);
}

```

## Work Experience

I believe that my biggest work experience is Sunset Forest game development I previously mentioned. It has been going since the summer of 2020 and is planned to be finished by the end of this summer. You can try the [current build](https://petrik33.itch.io/sunset-forest) which dates back to the 3rd of May.

## Education

- Student of BSU FAMCS (1st course)
- RS-School JS/Front-End - Stage0 (in progress)
- Game Maker self-education
- [MDN Web Docs](https://developer.mozilla.org/ru/) ["HTML - structuring the web"](https://developer.mozilla.org/ru/docs/Learn/HTML) course
- [Web.dev](https://web.dev/) [learn CSS](https://web.dev/i18n/ru/learn/css/) course

## Languages

### English

10 years of studying with personal teacher and 2 years of constant speaking practice with native speakers and other foreigners speaking English.

- B2+ level according to my personal experience and self-assessment
- C1 level of English according to EPAM Examinator Test

![Test completion screenshot](<./Images/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%20(978).png>)

### Others

- Russian - native speaker
- Belarusian - secret admirer
- Spanish - Duolingo 1st chapter (the owl made me write it)
