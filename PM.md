# Inloggningssystem | wsp1  | Post Mortem 

- titel: Login ALC
- tagline: Världens bästa inloggning
- url: N/A
- git: https://github.com/Alex-mp4/wsp1-login

## Inledning
Målet med denna uppgift var att skapa ett inloggningsystem med hjälp av npm, node, express, nunjucks, mysql (databas), router, views och sessions (samt sass). Dessutom ska man kunna skapa en användare och radera den. Arbetet gjordes i grupp med fyra klasskamrater (Nizar Dawood, Tim Fagerdal, Tim Nilsson) med endast en dator. För att säkerhetställa processen användes färdiggjorda tester för att varje del ska funka som det ska. 

## Bakgrund
Först och framförallt skapade vi en planering för hur programmet bör fungera, så som; vilka delar hänger ihop? Vilka sidor kommer vi behöva använda? Vilka funktioner ska vi fokusera på? Dessutom tittade vi igenom vad dessa grejar ska göra och vilka variabler de ska ta hand om. Denna planering kan du finna längst upp i "plandoc.md" dokumentet.

Vi körde sedan på med självaste kodandet. Test 1 var början och dessa implementationer var långt ifrån komplicerade. Dock, som jag nämner i negativa erfarenheter nedan, fanns det ändå vissa fundamentala problem med hur vi väl jobbade. Detta fixades till slut, men att kalla processen felfri hade varit en lögn. Implementationerna var för det mesta set-up element, såsom HTML-element, kopplade views och databas. Samt att kunna hasha lösenord för att göra hela processen mer säker. Sedan var det mer heavy-duty kodning på gång. Skapandet av ett program som jämför användarnamn och lösenord med innehållet på databasen. Självaste "bcrypt compare" koden tog en stund att förstå, men när vi väl gjorde det funkade allting perfekt. Främst glömde vi helt enkelt att göra en req.body. Nåja.

Sedan påbörjades sessionsarbete. Med denna funktion behövde personer vara inloggade (vilket skapar en session) för att kunna se profilen. Nu slipper vi problemet att folk kan hamna på profilsidan utan att ha en profil. Dock kunde man inte logga ut. Så vi fixade det näst!

Därefter skapade vi ett registersystem. För att detta ska inte vara fel behövde vi kolla om användarnamnet redan finns i databasen. Vi kopierade gammal kod som gjorde jämförelser med databasen (login). Däremot fanns det små ändringar som krävdes. Sedan blev vi klara och kunda göra extra arbete i form av delete user, som direkt tar bort en viss användare från databasen.

## Negativa erfarenheter
Jag bytte plats på dessa två erfarenheterna för att lägga dem i kronologisk ordning. Alltså; det negativa hände först. I början av det här projektet kändes det som om vi blev utslängd i djupt vatten. Våran kunskap i javascript var inte fullkommligt perfekt och tankesättet var annorlunda för oss. Det vill säga, ifall vi hade fått en kort run-through på hur testerna fungerade hade saker gått smidigare. Exempelvist förvirrade vi koden i testet för exempelkod; sådant vi skulle potentiellt kunnat använda. Allting i början gick segt, helt enkelt. Dessutom var ordningen och uppbyggnaden av kod lite främmande för oss under vissa tillfällen. Vi fastande i loopar av felmeddelanden vi inte riktigt förstod och allt därimellan.

## Positiva erfarenheter
Dock, på grund av detta kommer vi sedan vidare till de positiva erfarenheterna. När vi väl lyckades med Test 2 så började vi äntligen förstå processen. Vi hamnade i ett slags flow. Vi kunde återanvända kod vi väl fattade samt blev strukturella element av koden begripen. Det vill säga att vid halvvägspunkten rullade allting på band helt plötsligt. Från vad jag såg under den tiden var vi ganska långt bak jämfört med resten av grupperna, men därefter sprang vi förbi och hann lägga till extra funktioner (à la "delete user"). Då försvann majoriteten av all stress. Dessutom var upplägget av uppgiften kul att hålla på med. Faktumet att vi satt i grupper och kunde diskutera eller bolla idéer gjorde att bättre arbetsflyt. Olika perspektiv skapade fler tankar.

## Sammanfattning
Vi har alltså skapat ett program i grupper som kan skapa en användare, logga in en användare och radera en användare. Allt detta gjordes stegvist med hjälp av färdiggjorde tester. I början gick det sisådär, men ju längre vi kom så fungerade allting bättre och bättre. Vare sig våra huvuden eller programmen i sig. Jag har lärt mig mycket om node samt strukturen på javascript program som använder sig av routers.