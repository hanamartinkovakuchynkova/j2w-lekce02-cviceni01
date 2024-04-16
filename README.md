# Lekce 2 – datum a čas

Úvodní webová stránka bude obsahovat dva odkazy – na stránku s aktuálním datem a stránku s aktuálním časem. Dále budou na webu dvě stránky – stránka na adrese
`/datum` bude zobrazovat aktuální datum, stránka na adrese `/cas` bude zobrazovat aktuální čas (v okamžiku načtení stránky). V úvodní webové stránce je vložen
CSS framework [Bootstrap](https://getbootstrap.com). 

Pozor na to, že Freemarker pracuje interně se starší třídou `java.util.Date`, která nerozlišuje, zda se jedná o datum, čas nebo datum a čas.
Proto musíme Freemarkeru vždy říci, zda má s hodnotou pracovat jako s datem, časem nebo jako s datem a časem dohromady:
```freemarker
${x?date} → pracuje s hodnotou jako s datem
${x?time} → pracuje s hodnotou jako s časem
${x?datetime} → pracuje s hodnotou jako s datem a časem
```

1. Použij toto repository jako šablonu (Use this template), ze které si vytvoříš repository ve svém účtu na GitHubu.
1. Naklonuj si repository **ze svého účtu** na GitHubu na lokální počítač.
1. Úvodní stránka `static/index.html` už je připravená.
1. Vytvoř kontrolér – třídu `cz.czechitas.java2webapps.lekce2.controller.MainController`.
1. V kontroléru budou dvě metody – jedna bude navázána na cestu `/datum`, druhá na cestu `/cas`.
1. Obě metody budou vracet `ModelAndView`, view bude pro každou metodu jiné.
1. Metoda pro výpis data vloží do modelu aktuální datum `LocalDate.now()`.
1. Ve view musíme Freemarkeru říci, že se jedná o datum: `datum?date`.
1. Metoda pro výpis času vloží do modelu čas `LocalTime.now()`.
1. Ve view musíme Freemarkeru říci, že se jedná o čas: `cas?time`.
1. Pro zobrazení velkého nápisu lze použít následující třídy z Bootstrapu:   
   ```html
   <h1 class="display-1 fw-bold">Nápis</h1>
   ```
1. Zkontroluj výsledek v prohlížeči.

## Mohlo by se hodit
* odkaz na stránku [Lekce 2](https://java.czechitas.cz/2024-jaro/java-2-online/lekce-2.html)
* Freemarker [date, time, datetime](https://freemarker.apache.org/docs/ref_builtins_date.html#ref_builtin_date_datetype)
* CSS framework [Bootstrap](https://getbootstrap.com)
* balík [java.time](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/time/package-summary.html)
