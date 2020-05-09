##Точка с запятой — ОБЯЗАТЕЛЬНА

    // bad
	let luke = {}
	let leia = {}
	[luke, leia].forEach(jedi => jedi.father = 'vader')

	// good
	let luke = {};
	let leia = {};
	[luke, leia].forEach((jedi) => {
	  jedi.father = 'vader';
	});


##Горизонтальное выравнивание не рекомендуется

*Такая практика допустима, но, в целом, не рекомендуется «стилем» Google. Не следует продолжать горизонтальное выравнивание даже в местах, где оно уже применялось.*

	// bad
	{
	  tiny:   42,  
	  longer: 435, 
	};

	// good
	{
	  tiny: 42, 
	  longer: 435,
	};


##Предпочтение стрелочным функциям

*Стрелочные функции делают синтаксис лаконичным и устраняют некоторые трудности с ним. Отдавайте предпочтение стрелочным функциям, вместо ключевого слова function, особенно для вложенных функций.*

	// bad
	[1, 2, 3].map(function (x) {
	  const y = x + 1;
	  return x * y;
	});

	// good
	[1, 2, 3].map((x) => {
	  const y = x + 1;
	  return x * y;
	});


##Имена констант должны быть ЗАГЛАВНЫМИ_БУКВАМИ и через нижнее подчёркивание

*Для неизменных величин — НЕИЗМЕННО_ПРАВИЛО: всё заглавными, а слова через подчёркивание.*

	// bad
	const number = 5;

	// good
	const NUMBER = 5;


##Одна переменная за раз

*Каждое объявление локальной переменной объявляет только одну переменную: такие объявления, как let a = 1, b = 2; не используются.*

	// bad
	let a = 1, b = 2, c = 3;

	// good
	let a = 1;
	let b = 2;
	let c = 3;


##Используйте одинарные кавычки, а не двойные

*Обычные строковые литералы разделяются одинарными кавычками (‘), а не двойными (“).*

	// bad
	let directive = "No identification of self or mission."
	// bad
	let saying = 
	'Say it ain\u0027t so.';

	// good
	let directive = 'No identification of self or mission.';
	// good
	let saying = `Say it ain't so`;


##Длина строки

*Никто не любит читать длинные горизонтальные строки кода. Лучше всего разбивать их*

	// bad
	let str = 'Рабочая группа TC39 организации Ecma International - это группа JavaScript-разработчиков, теоретиков и авторов движков JavaScript, которые вместе с обществом нимаются поддержкой и развитием языка JavaScript.';

	// good
	let str = `
    Рабочая группа TC39 организации Ecma International -
    это группа JavaScript-разработчиков, теоретиков и авторов движков JavaScript,
    которые вместе с сообществом занимаются поддержкой и развитием языка JavaScript.`;


##Не используйте line continuations для длинных строк

*Не прерывайте строку внутри строкового литерала обратной косой чертой, в обычных или шаблонных строковых литералах. Несмотря на то, что ES5 допускает это, могут появится неприятные ошибки, если после косой черты окажется пробел. Это будет незаметно при чтении.*

	// bad (sorry, this doesn't show up well on mobile)
	const longString = 'This is a very long string that \
	    far exceeds the 80 column limit. It unfortunately \
	    contains long stretches of spaces due to how the \
	    continued lines are indented.';

	// good
	const longString = 'This is a very long string that ' + 
	    'far exceeds the 80 column limit. It does not contain ' + 
	    'long stretches of spaces since the concatenated ' +
	    'strings are cleaner.';


##Используйте шаблонные строки вместо конкатенации.

*Используйте шаблонные строки (разделённые символом \`) вместо конкатенации комплексных строк, особенно если используется несколько строковых литералов. Шаблонные строки могут занимать несколько строк.* 
 
	// bad
	function sayHi(name) {
	  return 'How are you, ' + name + '?'
	}
	// bad
	function sayHi(name) {
	  return ['How are you, ', name, '?'].join()
	}
	// bad
	function sayHi(name) {
	  return `How are you, ${ name }?`
	}

	// good
	function sayHi(name) {
	  return `How are you, ${name}?`
	} 


##Используйте пробелы вместо табуляции

*Помимо символа конца строки, символ горизонтального пробела ASCII (0x20), единственный разделитель, который следует использовать в любом месте исходного файла. Это означает, что символы табуляции не используются для отступов.*

	// bad
	function foo() {
	∙∙∙∙let name;
	}
	// bad
	function bar() {
	∙let name;
	}

	// good
	function baz() {
	∙∙let name;
	}

