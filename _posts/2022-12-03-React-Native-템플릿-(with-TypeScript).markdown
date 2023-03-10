<aside>
π£ μλ‘μ΄ νλ‘μ νΈλ₯Ό μν ννλ¦Ώμ λ§λλ κ³Όμ μ μ λ¦¬νμ΅λλ€.
</aside>

## 1. νλ‘μ νΈ μμ±

### π»Β Expoλ₯Ό μ΄μ©ν΄μ React Native νλ‘μ νΈλ₯Ό μμ±ν©λλ€.

{% highlight bash %}
npx create-expo-app --template
{% endhighlight %}

TypeScriptμ react-navigationμ μ΄μ©ν λͺ κ°μ μμ μ€ν¬λ¦°κ³Ό ν­μ ν¬ν¨ν ννλ¦Ώ μ΅μμ μ ν ν νλ‘μ νΈ μ΄λ¦μ μλ ₯ν©λλ€.

### π©βπ»Β μ€ν λ°©λ²

{% highlight bash %}
npx expo start
i # iOS
a # android
{% endhighlight %}


## 2. ESLint, Prettier μ€μ 

λμ μ½λ νλ¦¬ν°μ μνν νμμ μν μΌκ΄μ μΈ μ½λ μ€νμΌμ μν λκ΅¬ λ κ°μ§λ₯Ό μΆκ°ν©λλ€.

### βΒ κ΄λ ¨ λΌμ΄λΈλ¬λ¦¬μ νλ¬κ·ΈμΈμ μ€μΉν©λλ€.


{% highlight bash %}
npm install --save-dev eslint @typescript-eslint/eslint-plugin @typescript-eslint/parser
npm install --save-dev eslint-plugin-react@latest eslint-plugin-react-native@latest
{% endhighlight %}

{% highlight bash %}
npm install --save-dev prettier eslint-config-prettier eslint-plugin-prettier
{% endhighlight %}

### βΒ root λλ ν λ¦¬μ ESLint μ€μ μ μν `.eslintrc.js`Β νμΌμμΆκ°ν©λλ€.

{% highlight jsx %}
module.exports = {
env: {
browser: true,
es2021: true,
node: true,
},
extends: [
'eslint:recommended',
'plugin:prettier/recommended',
'plugin:react/recommended',
'plugin:@typescript-eslint/recommended',
],
overrides: [],
parser: '@typescript-eslint/parser',
parserOptions: {
ecmaVersion: 'latest',
sourceType: 'module',
},
plugins: ['react', 'react-native', '@typescript-eslint'],
rules: {
'eslint-comments/no-unlimited-disable': 0,
'eslint-comments/no-unused-disable': 0,
'react/no-unescaped-entities': 0,
'@typescript-eslint/no-namespace': 0,
'react/react-in-jsx-scope': 'off',
},
};
{% endhighlight %}

### βΒ root λλ ν λ¦¬μ Prettier μ€μ μ μν `.prettierrc.js` νμΌμ μΆκ°ν©λλ€.

{% highlight jsx%}
module.exports = {
// λ¬Έμμ΄μ νλ°μ΄ν(')
singleQuote: true,
// μ½λ λ§μ§λ§μ μΈλ―Έμ½λ‘  μΆκ°
semi: true,
// ν­ λμ  μ€νμ΄μ€λ° μ¬μ©
useTabs: false,
// λ€μ¬μ°κΈ° λλΉ
tabWidth: 2,
// νν μ½€λ§ κ°λ₯ν κ³³μ λͺ¨λ μ¬μ©
trailingComma: 'all',
// μ½λ νμ€ maximum λλΉ
printWidth: 80,
// νμ΄ν ν¨μκ° νλμ λ§€κ°λ³μλ₯Ό λ°μ λ κ΄νΈλ₯Ό μλ΅
arrowParens: 'avoid',
// EoF λ°©μ, OS λ³λ‘ μ²λ¦¬ λ°©μμ΄ λ€λ¦
endOfLine: 'auto',
};
{% endhighlight %}

### βΒ package.json scriptsμ μλ λ΄μ©μ μΆκ°ν©λλ€.

{% highlight json %}
"lint": "tsc --noEmit && eslint --ext .js,.jsx,.ts,.tsx ./",
"lint:fix": "eslint --fix '**/*.{ts,tsx,js,jsx}'",
"prettier": "npx prettier --write **/*.{js,jsx,ts,tsx,json} && npx prettier --write *.{js,jsx,ts,tsx,json}"
{% endhighlight %}


### βΒ ESLint μ€μ μ΄ μ λλμ§ νμ€νΈ

{% highlight json %}
npm run lint
{% endhighlight %}

### βΒ Prettierλ νμΌ μμ  ν save ν  λλ§λ€ μ μ© λλλ‘ μ€μ ν©λλ€.

IntelliJ β Preferences β Languages & Frameworks β Prettier

Run for files μλ **On save** μ²΄ν¬ λ°μ€ μ ν!

## 3. styled-component μ€μ 

### πΒ styled-componentsλ₯Ό μ€μΉν©λλ€.


{% highlight bash %}
npm install styled-components
{% endhighlight %}

### πΒ DefinitelyTypedμ λ±λ‘λ νμ μ μλ₯Ό μ€μΉν©λλ€.

DefinitelyTypedλ TypeScriptμ νμ κ²μ¬ μΈν°νμ΄μ€λ₯Ό μ κ³΅νλ λ¦¬ν¬μ§ν°λ¦¬ μλΉμ€λ‘ λ±λ‘λ νμ μ λ¦¬ λ΄μ©μ μ½κ² λ΄λ €λ°μ μ¬μ©ν  μ μμ΅λλ€. styled-componentsμ κ²½μ° μ»€λ?€λν°μμ μ λ¦¬ν νμ μ μκ° λ±λ‘λμ΄ μμ΅λλ€.


{% highlight bash %}
npm install --save-dev @types/styled-components @types/styled-components-react-native
{% endhighlight %}

tsconfigμ νμμ μ μνλ κ²½μ°, μλ μμμ κ°μ΄ typesμ `styled-components-react-native`λ₯Ό μΆκ°ν©λλ€.


{% highlight bash %}
"types": ["jest", "styled-components-react-native"],
{% endhighlight %}

### πΒ styled-component Babel νλ¬κ·ΈμΈμ μ€μΉν©λλ€.

μλ² μΈ‘ λ λλ§, μ€νμΌ μ΅μν λ° λ λμ λλ²κΉ νκ²½μ λν μ§μμ΄ μΆκ°λ©λλ€.

{% highlight bash %}
npm install --save-dev babel-plugin-styled-components
{% endhighlight %}

## πΒ μ°Έκ³  λ§ν¬

- [styled-components: API Reference](https://styled-components.com/docs/api#typescript)
- [https://github.com/DefinitelyTyped/DefinitelyTyped](https://github.com/DefinitelyTyped/DefinitelyTyped
  )

