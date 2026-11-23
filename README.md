<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<meta name="theme-color" content="#171614">
<title>go on</title>
<style>
:root{
 --bg:#171614;--panel:#22201d;--panel2:#2b2823;
 --gold:#c6a56a;--gold2:#e0c18a;--blue:#719ec4;
 --text:#eee9df;--muted:#aaa397;--line:#494237;
 --green:#829b78;--red:#bb7770;--radius:15px
}
*{box-sizing:border-box}
body{margin:0;background:var(--bg);color:var(--text);font-family:Arial,Helvetica,sans-serif;line-height:1.5}
button,input,select,textarea{font:inherit}
button{cursor:pointer;border:1px solid var(--line);border-radius:10px;padding:10px 14px;background:var(--panel2);color:var(--text)}
button:hover{border-color:var(--gold)}
button:disabled{opacity:.4;cursor:not-allowed}
button.primary{background:var(--gold);color:#171614;border-color:var(--gold);font-weight:bold}
button.danger{border-color:#8c4c49;color:#e9aaa3}
button.small{padding:6px 10px;font-size:12px}
input,select,textarea{width:100%;padding:11px;border:1px solid var(--line);border-radius:9px;background:#191815;color:var(--text);margin:5px 0 12px}
textarea{min-height:100px;resize:vertical}
label{color:var(--muted);font-size:13px;display:block}
header{padding:20px 18px 12px;text-align:center;border-bottom:1px solid var(--line)}
.logo{font-family:Georgia,serif;font-size:38px;letter-spacing:4px;color:var(--gold2)}
nav{display:flex;gap:6px;padding:10px;overflow-x:auto;position:sticky;top:0;z-index:5;background:rgba(23,22,20,.97);border-bottom:1px solid var(--line)}
nav button{white-space:nowrap;font-size:12px;padding:9px 12px}
nav button.active{background:var(--gold);color:#171614;border-color:var(--gold)}
main{max-width:980px;margin:auto;padding:18px 14px 90px}
.page{display:none}.page.active{display:block}
h1,h2,h3{font-family:Georgia,serif;font-weight:normal}
h1{font-size:27px;color:var(--gold2)}
h2{font-size:22px;color:var(--gold2)}
h3{font-size:18px}
p{color:#ded8cc}
.muted{color:var(--muted)}
.card{background:var(--panel);border:1px solid var(--line);border-radius:var(--radius);padding:17px;margin:13px 0}
.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:12px}
.row{display:flex;gap:9px;flex-wrap:wrap;align-items:center}
.row>*{flex:1}
.row .fixed{flex:0 0 auto}
.stat{text-align:center}
.stat strong{display:block;font-size:25px;color:var(--gold2)}
.ring{width:145px;height:145px;border-radius:50%;margin:12px auto;display:grid;place-items:center;background:conic-gradient(var(--gold) var(--progress,0%),#494237 0);position:relative}
.ring.blue{background:conic-gradient(var(--blue) var(--progress,0%),#494237 0)}
.ring:before{content:"";position:absolute;inset:10px;border-radius:50%;background:var(--panel)}
.ring-content{position:relative;text-align:center}
.ring-content strong{font-size:29px;color:var(--gold2);display:block}
.word{font-size:23px;color:var(--gold2);font-weight:bold}
.translation{font-size:15px;color:var(--muted)}
.example{font-style:italic;color:#ded8cc}
.tag{display:inline-block;border:1px solid var(--line);color:var(--gold2);padding:3px 8px;border-radius:20px;font-size:11px;margin:2px}
.notice{font-size:12px;color:var(--muted)}
hr{border:0;border-top:1px solid var(--line);margin:17px 0}
.word-item{padding:12px 0;border-bottom:1px solid var(--line)}
.word-item:last-child{border-bottom:0}
.picture-card{min-height:160px;display:flex;flex-direction:column;justify-content:space-between}
.comic{border:2px solid #f2d34f;background:radial-gradient(#17161466 1px,transparent 1px),linear-gradient(145deg,#e94c70,#efa32f 55%,#39b8c9);background-size:7px 7px,cover;color:#171614;border-radius:12px;padding:17px;font-weight:bold;box-shadow:4px 4px 0 #c6a56a}
.comic .word{color:#171614}
.answer{margin-top:10px;padding:12px;background:#191815;border-radius:9px}
.hidden{display:none!important}
.progress{height:8px;background:#494237;border-radius:20px;overflow:hidden;margin:10px 0}
.progress span{display:block;height:100%;background:var(--gold);width:0;transition:width .2s}
.feedback{padding:12px;border-radius:10px;margin:12px 0}
.good{background:#203126;border:1px solid #536e51}
.bad{background:#382322;border:1px solid #87504a}
.choice{display:grid;gap:8px;margin:12px 0}
.choice button{text-align:left}
.choice button.chosen{border-color:var(--gold);background:#393126}
.tabs{display:flex;gap:7px;overflow-x:auto;margin:10px 0}
.tabs button{white-space:nowrap}
.tabs button.active{border-color:var(--gold);color:var(--gold2)}
.exercise-word{font-family:Georgia,serif;font-size:29px;color:var(--gold2);margin:18px 0}
.empty{padding:18px;text-align:center;color:var(--muted)}
footer{text-align:center;color:var(--muted);font-size:11px;padding:25px}
@media(min-width:700px){main{padding-top:25px}nav{justify-content:center}}
</style>
</head>
<body>
<header><div class="logo">go on</div></header>

<nav id="navigation">
 <button class="active" data-page="home">Start</button>
 <button data-page="today">Heute</button>
 <button data-page="learn">Lernen</button>
 <button data-page="tests">Schule & Tests</button>
 <button data-page="library">Bibliothek</button>
 <button data-page="review">Wiederholen</button>
 <button data-page="settings">⚙</button>
</nav>

<main>
<section id="home" class="page active">
 <h1>Welcome back.</h1>
 <p class="muted">Jeder Tag bringt dich ein Stück weiter.</p>
 <div class="card">
  <div class="grid">
   <div class="stat">
    <div class="ring" id="wordRing"><div class="ring-content"><strong id="wordProgress">0/10</strong><span class="muted">Wörter</span></div></div>
   </div>
   <div class="stat">
    <div class="ring blue" id="sentenceRing"><div class="ring-content"><strong id="sentenceProgress">0/10</strong><span class="muted">Sätze</span></div></div>
   </div>
  </div>
  <div class="grid">
   <div class="stat"><strong id="homeWords">0</strong><span class="muted">Gespeicherte Wörter</span></div>
   <div class="stat"><strong id="homeSentences">0</strong><span class="muted">Gespeicherte Sätze</span></div>
   <div class="stat"><strong id="homeTexts">0</strong><span class="muted">Texte gelesen</span></div>
  </div>
 </div>
 <div class="grid">
  <div class="card"><h3>Today's words</h3><p>Deine zehn neuen Wörter für heute.</p><button class="primary" onclick="showPage('today')">Start learning</button></div>
  <div class="card"><h3>Smart Revision</h3><p>Wiederhole Wörter und Sätze mit dem Rotationssystem.</p><button onclick="showPage('review')">Start revision</button></div>
  <div class="card"><h3>Reading</h3><p>Englische Texte, neue Wörter und Verständnisfragen.</p><button onclick="showPage('learn');setLearnTab('read')">Read now</button></div>
  <div class="card"><h3>Tests</h3><p>Teste dein Englisch in verschiedenen Bereichen.</p><button onclick="showPage('tests')">Start test</button></div>
 </div>
 <div class="card"><h2>Deine Lernstatistik</h2><div id="homeStats"></div></div>
</section>

<section id="today" class="page">
 <h1>Today's lesson</h1>
 <p class="muted">Zehn Wörter und zehn Alltagssätze. Die Wörter stammen aus den Lesetexten dieser Lernversion.</p>
 <div class="card">
  <div class="row"><span class="tag">10 new words</span><span class="tag" id="todayDate"></span></div>
  <div id="dailyWords"></div>
  <button class="primary" onclick="startDaily('word')">Wörter lernen</button>
 </div>
 <div class="card">
  <h2>Ten everyday sentences</h2>
  <div id="dailySentences"></div>
  <button class="primary" onclick="startDaily('sentence')">Sätze lernen</button>
 </div>
</section>

<section id="learn" class="page">
 <h1>Lernen</h1>
 <div class="tabs" id="learnTabs">
  <button class="active" data-tab="translate">Übersetzen</button>
  <button data-tab="read">Lesen</button>
  <button data-tab="speak">Sprechen</button>
  <button data-tab="listen">Hören</button>
  <button data-tab="pictures">Bilder</button>
  <button data-tab="write">Schreiben</button>
  <button data-tab="subtitles">Untertitel</button>
 </div>
 <div id="learnContent"></div>
</section>

<section id="tests" class="page">
 <h1>Schule & Tests</h1>
 <div class="card">
  <h2>Eigenen Test zusammenstellen</h2>
  <label>Testbereich</label>
  <select id="testCategory">
   <option value="vocab">Vokabeln</option>
   <option value="sentences">Sätze & Übersetzung</option>
   <option value="grammar">Grammatik</option>
   <option value="reading">Leseverständnis</option>
   <option value="mixed">Gemischter Test</option>
  </select>
  <label>Schwierigkeitsgrad</label>
  <select id="testLevel"><option>A2</option><option selected>B1</option><option>B2</option><option>C1</option></select>
  <label>Anzahl der Aufgaben</label>
  <select id="testCount"><option>5</option><option selected>10</option><option>20</option></select>
  <button class="primary" onclick="startChosenTest()">Test starten</button>
 </div>
 <div class="card">
  <h2>Grammatikthemen</h2>
  <div class="tabs" id="grammarTabs"></div>
  <div id="grammarInfo" class="muted">Wähle ein Thema aus.</div>
 </div>
 <div class="card"><h2>Deine Ergebnisse</h2><div id="testStats"></div></div>
</section>

<section id="library" class="page">
 <h1>Bibliothek</h1>
 <div class="tabs" id="libraryTabs">
  <button class="active" data-tab="words">Wörter</button>
  <button data-tab="sentences">Sätze</button>
  <button data-tab="texts">Texte</button>
  <button data-tab="marked">Markiert</button>
  <button data-tab="skipped">Skip it</button>
 </div>
 <div class="card">
  <div class="row"><input id="librarySearch" placeholder="Suchen …" oninput="renderLibrary()"><button class="fixed" onclick="addLibraryEntry()">＋ Hinzufügen</button></div>
  <div id="libraryContent"></div>
 </div>
 <div class="card">
  <h2>Datensicherung</h2>
  <p>Exportiere deine Wörter, Sätze, Texte, Lernstände und Einstellungen.</p>
  <div class="row"><button onclick="exportData()">Backup exportieren</button><button onclick="document.getElementById('importFile').click()">Backup importieren</button></div>
  <input type="file" id="importFile" accept="application/json" class="hidden" onchange="importData(event)">
 </div>
</section>

<section id="review" class="page">
 <h1>Wiederholen</h1>
 <div class="card">
  <h2>Smart Revision</h2>
  <p>Richtige Antworten werden mit längeren Abständen wiederholt. Falsche Antworten kommen früher zurück.</p>
  <label>Was möchtest du wiederholen?</label>
  <select id="reviewType"><option value="word">Wörter</option><option value="sentence">Sätze</option><option value="all">Alles gemischt</option></select>
  <label>Anzahl</label>
  <select id="reviewCount"><option>5</option><option selected>10</option><option>20</option><option value="all">Alle</option></select>
  <label>Übersetzungsrichtung</label>
  <select id="reviewDirection"><option value="mixed">Gemischt</option><option value="en-de">Englisch → Deutsch</option><option value="de-en">Deutsch → Englisch</option></select>
  <button class="primary" onclick="startReview()">Wiederholung starten</button>
 </div>
 <div class="card"><h2>Deine Wiederholungsfälligkeiten</h2><div id="dueStats"></div></div>
 <div class="card"><h2>Letzte Antworten</h2><div id="recentHistory"></div></div>
</section>

<section id="settings" class="page">
 <h1>Einstellungen</h1>
 <div class="card">
  <h2>Aufgabenablauf</h2>
  <label>Nach der Antwort</label>
  <select id="autoNext"><option value="false">Manuell – ich drücke „Nächste Aufgabe“</option><option value="true">Automatisch weitergehen</option></select>
  <label>Wartezeit vor der nächsten Aufgabe</label>
  <select id="autoDelay"><option value="2">2 Sekunden</option><option value="3">3 Sekunden</option><option value="5">5 Sekunden</option><option value="8">8 Sekunden</option></select>
  <label>Standard-Schwierigkeitsgrad</label>
  <select id="defaultLevel"><option>A2</option><option selected>B1</option><option>B2</option><option>C1</option></select>
  <button class="primary" onclick="saveSettings()">Einstellungen speichern</button>
 </div>
 <div class="card">
  <h2>Audio</h2>
  <label>Englische Aussprache</label>
  <select id="voice"><option value="en-GB">British English</option><option value="en-US">American English</option></select>
  <label>Sprachgeschwindigkeit</label>
  <input type="range" min=".6" max="1.2" step=".1" id="speechRate" value=".9">
  <button onclick="speakText('Welcome back. Let us practise English.')">Stimme testen</button>
 </div>
 <div class="card">
  <h2>Deine Daten</h2>
  <p class="notice">Die Daten werden lokal in diesem Browser gespeichert. Für die Nutzung auf mehreren Geräten ist später eine Synchronisierung über einen Server erforderlich.</p>
  <button class="danger" onclick="resetData()">Alle Lerninhalte zurücksetzen</button>
 </div>
</section>

<div id="exerciseScreen" class="hidden"></div>
</main>
<footer>go on · Learn a little. Every day.</footer>

<script>
"use strict";

/* -------------------------------------------------------
   DATEN UND MIGRATION
------------------------------------------------------- */
const STORAGE_KEY="goOnData";

const WORD_SEED=[
 ["approach","Herangehensweise; sich nähern","We need a different approach.","B2","Society"],
 ["aware","bewusst","Are you aware of the problem?","B1","Everyday"],
 ["benefit","Vorteil; profitieren","Exercise has many benefits.","B1","Health"],
 ["challenge","Herausforderung","Learning a language is a challenge.","B1","Everyday"],
 ["consider","in Betracht ziehen","I will consider your idea.","B1","Everyday"],
 ["despite","trotz","Despite the rain, we went out.","B2","Everyday"],
 ["environment","Umwelt; Umgebung","We should protect the environment.","B1","Nature"],
 ["improve","verbessern","I want to improve my English.","A2","Everyday"],
 ["opportunity","Gelegenheit","This is a great opportunity.","B1","Everyday"],
 ["reliable","zuverlässig","She is a reliable person.","B2","Society"],
 ["evidence","Beweis; Beleg","There is little evidence for this claim.","B2","Science"],
 ["consequence","Folge","Every decision has consequences.","B2","Society"],
 ["independent","unabhängig","She became financially independent.","B2","Society"],
 ["maintain","aufrechterhalten","It is hard to maintain good habits.","B2","Health"],
 ["significant","bedeutend","There was a significant change.","B2","Society"],
 ["perspective","Perspektive","Try to see it from another perspective.","B2","Psychology"],
 ["behaviour","Verhalten","Human behaviour is complex.","B2","Psychology"],
 ["inequality","Ungleichheit","Inequality affects many communities.","C1","Society"],
 ["resilience","Widerstandsfähigkeit","Resilience helps people face difficulties.","C1","Psychology"],
 ["sustainable","nachhaltig","We need sustainable solutions.","C1","Nature"]
];

const SENTENCE_SEED=[
 ["Could you explain that again?","Könntest du das noch einmal erklären?","A2"],
 ["I am looking forward to seeing you.","Ich freue mich darauf, dich zu sehen.","B1"],
 ["It depends on what happens next.","Es hängt davon ab, was als Nächstes passiert.","B1"],
 ["I would rather stay at home tonight.","Ich würde heute Abend lieber zu Hause bleiben.","B1"],
 ["There is no point in worrying about it now.","Es hat keinen Sinn, sich jetzt darüber Sorgen zu machen.","B2"],
 ["The decision had a greater impact than expected.","Die Entscheidung hatte größere Auswirkungen als erwartet.","B2"],
 ["I used to find this difficult.","Früher fand ich das schwierig.","B1"],
 ["We should take the long-term consequences into account.","Wir sollten die langfristigen Folgen berücksichtigen.","B2"],
 ["What matters is how you respond to the situation.","Entscheidend ist, wie du auf die Situation reagierst.","B2"],
 ["The results suggest that further research is necessary.","Die Ergebnisse legen nahe, dass weitere Forschung notwendig ist.","C1"]
];

const TEXTS=[
 {id:"text-india",title:"India: A country of contrasts",category:"Culture",level:"B2",difficulty:"Anspruchsvoll",
 body:"India is one of the world's largest countries. Its society is shaped by many languages, religions and cultural traditions. Life can look very different from one region to another. Large cities have become important centres of technology, education and business. At the same time, many rural communities remain closely connected to agriculture and local traditions. Economic growth has created new opportunities, but poverty and unequal access to healthcare and education remain serious challenges. Understanding India requires looking beyond simple descriptions and paying attention to its regional diversity.",
 de:"Indien ist eines der größten Länder der Welt. Seine Gesellschaft wird von vielen Sprachen, Religionen und kulturellen Traditionen geprägt. Das Leben kann von einer Region zur anderen sehr unterschiedlich aussehen. Große Städte sind wichtige Zentren für Technologie, Bildung und Wirtschaft geworden. Gleichzeitig sind viele ländliche Gemeinschaften weiterhin eng mit Landwirtschaft und lokalen Traditionen verbunden. Das Wirtschaftswachstum hat neue Möglichkeiten geschaffen, aber Armut und ein ungleicher Zugang zu Gesundheitsversorgung und Bildung bleiben große Herausforderungen. Um Indien zu verstehen, muss man über einfache Beschreibungen hinausblicken und seine regionale Vielfalt beachten.",
 words:[["society","Gesellschaft"],["rural","ländlich"],["agriculture","Landwirtschaft"],["opportunity","Möglichkeit"],["unequal","ungleich"],["diversity","Vielfalt"],["challenge","Herausforderung"],["tradition","Tradition"],["access","Zugang"],["region","Region"]],
 questions:[["What are two important roles of large Indian cities?","Technology, education and business."],["Name two challenges mentioned in the text.","Poverty and unequal access to healthcare and education."]]},
 {id:"text-psychology",title:"Understanding human behaviour",category:"Psychology",level:"B2",difficulty:"Anspruchsvoll",
 body:"Human behaviour is influenced by emotions, experiences, values and social surroundings. People do not always react in the same way, even when they face similar situations. Good communication involves listening carefully, asking questions and expressing thoughts clearly. Disagreement does not have to become a conflict if people treat each other with respect. Self-awareness can help people recognise their own reactions and understand how their behaviour affects others.",
 de:"Menschliches Verhalten wird durch Gefühle, Erfahrungen, Werte und das soziale Umfeld beeinflusst. Menschen reagieren nicht immer gleich, selbst wenn sie mit ähnlichen Situationen konfrontiert sind. Gute Kommunikation bedeutet, aufmerksam zuzuhören, Fragen zu stellen und Gedanken klar auszudrücken. Unterschiedliche Meinungen müssen nicht zu einem Konflikt führen, wenn Menschen respektvoll miteinander umgehen. Selbstwahrnehmung kann Menschen helfen, ihre eigenen Reaktionen zu erkennen und zu verstehen, wie ihr Verhalten andere beeinflusst.",
 words:[["behaviour","Verhalten"],["influence","beeinflussen"],["surroundings","Umfeld"],["disagreement","Meinungsverschiedenheit"],["self-awareness","Selbstwahrnehmung"],["recognise","erkennen"],["respect","Respekt"],["reaction","Reaktion"]],
 questions:[["What influences human behaviour?","Emotions, experiences, values and social surroundings."],["What can self-awareness help people understand?","Their own reactions and how their behaviour affects others."]]},
 {id:"text-climate",title:"The changing climate",category:"Nature",level:"C1",difficulty:"Sehr anspruchsvoll",
 body:"Climate change is not merely an environmental issue; it also affects public health, infrastructure, food systems and economic stability. The effects are unevenly distributed, as communities differ in their exposure and ability to adapt. Effective responses therefore require both emissions reductions and measures that strengthen resilience. Scientific evidence can inform policy, but decisions also involve social priorities and economic trade-offs.",
 de:"Der Klimawandel ist nicht nur ein Umweltproblem; er betrifft auch die öffentliche Gesundheit, Infrastruktur, Ernährungssysteme und wirtschaftliche Stabilität. Die Auswirkungen sind ungleich verteilt, da sich Gemeinschaften hinsichtlich ihrer Gefährdung und Anpassungsfähigkeit unterscheiden. Wirksame Reaktionen erfordern daher sowohl eine Verringerung der Emissionen als auch Maßnahmen zur Stärkung der Widerstandsfähigkeit. Wissenschaftliche Erkenntnisse können politische Entscheidungen unterstützen, aber Entscheidungen beinhalten auch gesellschaftliche Prioritäten und wirtschaftliche Abwägungen.",
 words:[["infrastructure","Infrastruktur"],["unevenly","ungleichmäßig"],["exposure","Gefährdung"],["adapt","sich anpassen"],["emissions","Emissionen"],["resilience","Widerstandsfähigkeit"],["evidence","Belege"],["trade-off","Abwägung"]],
 questions:[["Why are the effects unevenly distributed?","Communities differ in their exposure and ability to adapt."],["What two kinds of responses are mentioned?","Emissions reductions and measures that strengthen resilience."]]},
 {id:"text-history",title:"History and social change",category:"History",level:"B1",difficulty:"Mittel",
 body:"History helps us understand how societies have changed over time. Political decisions, inventions and social movements can influence the lives of millions of people. Some changes happen slowly, while others transform everyday life within a few years. Looking at historical events from different perspectives can help us understand why people disagree about the present.",
 de:"Geschichte hilft uns zu verstehen, wie sich Gesellschaften im Laufe der Zeit verändert haben. Politische Entscheidungen, Erfindungen und soziale Bewegungen können das Leben von Millionen Menschen beeinflussen. Manche Veränderungen geschehen langsam, während andere den Alltag innerhalb weniger Jahre verändern. Historische Ereignisse aus unterschiedlichen Perspektiven zu betrachten, kann uns helfen zu verstehen, warum Menschen über die Gegenwart unterschiedlicher Meinung sind.",
 words:[["society","Gesellschaft"],["movement","Bewegung"],["invention","Erfindung"],["transform","verändern"],["perspective","Perspektive"]],
 questions:[["What can influence the lives of millions of people?","Political decisions, inventions and social movements."],["Why are different perspectives useful?","They help us understand disagreements about the present."]]},
 {id:"text-science",title:"How habits are formed",category:"Science",level:"B2",difficulty:"Mittel",
 body:"Habits develop when a behaviour is repeated in a stable context. Over time, the situation itself can trigger an action with less conscious effort. This process can be useful, but it also explains why unwanted routines are difficult to change. A practical strategy is to make a desired behaviour easy to start and repeat it consistently.",
 de:"Gewohnheiten entwickeln sich, wenn ein Verhalten in einem stabilen Zusammenhang wiederholt wird. Mit der Zeit kann die Situation selbst eine Handlung auslösen, ohne dass dafür viel bewusste Anstrengung nötig ist. Dieser Prozess kann nützlich sein, erklärt aber auch, warum unerwünschte Routinen schwer zu verändern sind. Eine praktische Strategie besteht darin, ein gewünschtes Verhalten leicht zu beginnen und es regelmäßig zu wiederholen.",
 words:[["habit","Gewohnheit"],["behaviour","Verhalten"],["stable","stabil"],["trigger","auslösen"],["conscious","bewusst"],["routine","Routine"],["consistently","regelmäßig"]],
 questions:[["What can trigger a habitual action?","A stable situation or context."],["What is one practical strategy?","Make the desired behaviour easy to start and repeat it consistently."]]}
];

const GRAMMAR={
 "Present Simple":{ex:"She works every day. / Do you speak English?",rule:"Für Gewohnheiten und allgemeine Tatsachen. Bei he, she und it bekommt das Vollverb normalerweise ein -s. Fragen werden mit do oder does gebildet.",q:[
 ["She ___ to work every day.",["go","goes","going"],"goes","Bei he/she/it kommt im Present Simple ein -s ans Verb."],
 ["___ you speak English?",["Do","Does","Are"],"Do","Bei you verwendet man do."],
 ["He doesn't ___ coffee.",["likes","like","liking"],"like","Nach doesn't steht die Grundform."]
 ]},
 "Past Simple":{ex:"I visited London last year.",rule:"Für abgeschlossene Handlungen in der Vergangenheit. Regelmäßige Verben erhalten -ed; unregelmäßige Verben haben eigene Formen.",q:[
 ["Yesterday, we ___ a film.",["watch","watched","have watched"],"watched","Yesterday zeigt eine abgeschlossene Vergangenheit."],
 ["She ___ to Berlin last week.",["go","went","gone"],"went","Go ist unregelmäßig: go – went – gone."],
 ["Did you ___ him?",["saw","see","seen"],"see","Nach did steht die Grundform."]
 ]},
 "Present Perfect":{ex:"I have lived here since 2020.",rule:"Have/has + past participle. Die Vergangenheit hat einen Bezug zur Gegenwart. Since bezeichnet einen Startpunkt, for einen Zeitraum.",q:[
 ["I have lived here ___ 2020.",["for","since","during"],"since","Since wird mit einem Startzeitpunkt verwendet."],
 ["She has ___ her keys.",["lose","lost","losing"],"lost","Nach has steht das past participle."],
 ["We ___ never been there.",["have","has","did"],"have","Bei we verwendet man have."]
 ]},
 "Future":{ex:"I will call you. / I am going to travel.",rule:"Will wird häufig für spontane Entscheidungen und Vorhersagen verwendet. Going to passt zu Plänen und erkennbaren Anzeichen.",q:[
 ["Look at those clouds! It ___ rain.",["will","is going to","would"],"is going to","Ein sichtbares Anzeichen spricht für going to."],
 ["I think she ___ pass the exam.",["will","is","did"],"will","Will eignet sich für eine Vorhersage."],
 ["We ___ visit them next weekend.",["are going to","was","have"],"are going to","Ein geplanter Besuch: are going to."]
 ]},
 "Conditionals":{ex:"If I had more time, I would travel.",rule:"Zero Conditional: allgemeine Tatsachen. First Conditional: reale Möglichkeit. Second Conditional: hypothetische Situation. Third Conditional: nicht mehr veränderbare Vergangenheit.",q:[
 ["If I had more time, I ___ travel.",["will","would","can"],"would","Second Conditional: would + Grundform."],
 ["If it rains, we ___ at home.",["stay","will stay","would stayed"],"will stay","First Conditional: If + Present, will + Grundform."],
 ["If I had known, I ___ helped.",["would have","will have","had"],"would have","Third Conditional: would have + past participle."]
 ]},
 "Passive Voice":{ex:"The book was written in 1998.",rule:"Das Passiv besteht aus einer Form von be und dem past participle. Es wird verwendet, wenn die Handlung oder das Ergebnis wichtiger ist als die handelnde Person.",q:[
 ["The letter ___ yesterday.",["sent","was sent","is sending"],"was sent","Simple Past Passive: was/were + past participle."],
 ["English ___ in many countries.",["speaks","is spoken","is speaking"],"is spoken","Present Passive: am/is/are + past participle."],
 ["The building ___ next year.",["will open","will be opened","opened"],"will be opened","Future Passive: will be + past participle."]
 ]},
 "Indirect Speech":{ex:"She said that she was tired.",rule:"In der indirekten Rede verschieben sich die Zeitformen häufig eine Stufe zurück, wenn das einleitende Verb in der Vergangenheit steht.",q:[
 ["He said: 'I am tired.' → He said he ___ tired.",["is","was","has"],"was","Das Present Simple wird hier zu Past Simple."],
 ["She said: 'I will call.' → She said she ___ call.",["will","would","can"],"would","Will wird in der indirekten Rede häufig zu would."],
 ["He asked me where I ___.",["live","lived","am living"],"lived","Die Frage wird in eine normale Satzstellung umgewandelt."]
 ]},
 "Prepositions":{ex:"She is interested in science.",rule:"Präpositionen folgen oft festen Verbindungen. Viele müssen gemeinsam mit dem jeweiligen Wort gelernt werden.",q:[
 ["She is interested ___ science.",["on","in","at"],"in","Interested in ist die feste Verbindung."],
 ["We arrived ___ the airport.",["at","in","to"],"at","Arrive at wird für einen konkreten Ort verwendet."],
 ["It depends ___ the weather.",["of","on","from"],"on","Depend on ist die richtige Verbindung."]
 ]},
 "Relative Clauses":{ex:"The woman who lives next door is a doctor.",rule:"Relative Clauses geben zusätzliche Informationen. Who bezieht sich auf Personen, which auf Dinge und that kann in vielen Fällen beide ersetzen.",q:[
 ["The woman ___ lives here is kind.",["which","who","where"],"who","Who bezieht sich auf Personen."],
 ["The book ___ I bought is interesting.",["who","where","that"],"that","That kann sich auf Dinge beziehen."],
 ["This is the place ___ we met.",["where","who","which"],"where","Where bezeichnet einen Ort."]
 ]},
 "Word Order":{ex:"She usually goes to work by bus.",rule:"Die normale englische Satzstellung ist Subject + Verb + Object. Häufigkeitsadverbien stehen meist vor dem Vollverb, aber nach be.",q:[
 ["Choose the correct sentence.",["Always I drink coffee.","I always drink coffee.","I drink always coffee."],"I always drink coffee.","Häufigkeitsadverbien stehen normalerweise vor dem Vollverb."],
 ["Choose the correct question.",["Where you live?","Where do you live?","Where live you?"],"Where do you live?","Fragen im Present Simple benötigen do/does."],
 ["Choose the correct order.",["She speaks very well English.","She speaks English very well.","She English speaks very well."],"She speaks English very well.","Das Objekt steht normalerweise nach dem Verb."]
 ]}
};

const PICTURES=[
 ["approach","Herangehensweise","🧭","We need a different approach."],
 ["opportunity","Gelegenheit","🚪","This is a great opportunity."],
 ["environment","Umwelt","🌳","We should protect the environment."],
 ["challenge","Herausforderung","⛰️","It was a difficult challenge."],
 ["reliable","zuverlässig","🤝","She is a reliable person."],
 ["evidence","Beweis","🔍","There is evidence to support the idea."],
 ["freedom","Freiheit","🕊️","Freedom is important."],
 ["resilience","Widerstandsfähigkeit","🌱","Resilience helps people recover."]
];

function freshData(){
 return {
  words:[],sentences:[],texts:[],skipped:[],history:[],
  settings:{autoNext:false,autoDelay:2,level:"B1",voice:"en-GB",rate:.9},
  daily:{date:"",wordIds:[],sentenceIds:[],learnedWords:[],learnedSentences:[],readTexts:[]},
  quizCount:0
 };
}
function loadData(){
 let raw;
 try{raw=JSON.parse(localStorage.getItem(STORAGE_KEY)||"null")}catch(e){raw=null}
 let d=freshData();
 if(!raw)return d;
 d={...d,...raw};
 d.settings={...freshData().settings,...(raw.settings||{})};
 d.words=Array.isArray(raw.words)?raw.words:[];
 d.sentences=Array.isArray(raw.sentences)?raw.sentences:[];
 d.texts=Array.isArray(raw.texts)?raw.texts:[];
 d.skipped=Array.isArray(raw.skipped)?raw.skipped:[];
 d.history=Array.isArray(raw.history)?raw.history:[];
 d.daily={...freshData().daily,...(raw.daily||{})};
 // Alte Einträge aus der bisherigen Version übernehmen.
 d.words=d.words.map((w,i)=>normaliseEntry(w,"word",i));
 d.sentences=d.sentences.map((s,i)=>normaliseEntry(s,"sentence",i));
 d.texts=d.texts.map((t,i)=>({...t,id:t.id||"oldtext-"+i,marked:!!t.marked}));
 // Frühere Lesetexte ergänzen, ohne bestehende zu überschreiben.
 TEXTS.forEach(t=>{if(!d.texts.some(x=>x.id===t.id))d.texts.push({...t,marked:false})});
 return d;
}
function normaliseEntry(x,type,i){
 return {
  ...x,id:x.id||type+"-"+i+"-"+Date.now(),
  en:x.en||x.word||"",de:x.de||x.meaning||"",
  example:x.example||"",level:x.level||"B1",
  category:x.category||x.cat||"Eigene",
  box:Number(x.box)||0,due:Number(x.due)||0,
  correct:Number(x.correct)||0,wrong:Number(x.wrong)||0,
  seen:Number(x.seen)||0,marked:!!x.marked,
  created:x.created||x.date||todayKey()
 };
}
let db=loadData();
let page="home",learnTab="translate",libraryTab="words";
let exercise=null,exerciseTimer=null,readingText=null;
let grammarSelected="Present Simple";

function save(){localStorage.setItem(STORAGE_KEY,JSON.stringify(db));updateHome()}
function todayKey(){let d=new Date();return d.getFullYear()+"-"+String(d.getMonth()+1).padStart(2,"0")+"-"+String(d.getDate()).padStart(2,"0")}
function uid(prefix="x"){return prefix+"-"+Date.now()+"-"+Math.random().toString(36).slice(2,7)}
function esc(s=""){return String(s).replace(/[&<>"']/g,c=>({"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"}[c]))}
function norm(s=""){return String(s).toLowerCase().normalize("NFD").replace(/[\u0300-\u036f]/g,"").replace(/[.,!?;:'"()]/g,"").replace(/\s+/g," ").trim()}
function shuffle(a){let x=[...a];for(let i=x.length-1;i>0;i--){let j=Math.floor(Math.random()*(i+1));[x[i],x[j]]=[x[j],x[i]]}return x}
function pct(a,b){return Math.min(100,Math.round(a/Math.max(1,b)*100))}
function setRing(id,value){document.getElementById(id).style.setProperty("--progress",pct(value,10)+"%")}

function ensureDaily(){
 if(db.daily.date!==todayKey()){
  db.daily={date:todayKey(),wordIds:[],sentenceIds:[],learnedWords:[],learnedSentences:[],readTexts:[]};
  save();
 }
 if(!db.daily.wordIds.length){
  let known=new Set(db.words.map(x=>norm(x.en)));
  let candidates=WORD_SEED.filter(x=>!known.has(norm(x[0])));
  db.daily.wordIds=shuffle(candidates.length?candidates:WORD_SEED).slice(0,10).map((x,i)=>x[0]);
 }
 if(!db.daily.sentenceIds.length)db.daily.sentenceIds=shuffle(SENTENCE_SEED).slice(0,10).map(x=>x[0]);
 save();
}
function updateHome(){
 if(!db.daily.date)ensureDaily();
 let w=db.daily.learnedWords.length,s=db.daily.learnedSentences.length;
 document.getElementById("wordProgress").textContent=w+"/10";
 document.getElementById("sentenceProgress").textContent=s+"/10";
 setRing("wordRing",w);setRing("sentenceRing",s);
 document.getElementById("homeWords").textContent=db.words.length;
 document.getElementById("homeSentences").textContent=db.sentences.length;
 document.getElementById("homeTexts").textContent=db.daily.readTexts.length;
 let total=db.history.filter(x=>x.correct!==null).length;
 let correct=db.history.filter(x=>x.correct===true).length;
 document.getElementById("homeStats").innerHTML=
 `<div class="grid"><div class="stat"><strong>${total}</strong><span class="muted">Beantwortete Aufgaben</span></div><div class="stat"><strong>${total?pct(correct,total):0}%</strong><span class="muted">Trefferquote</span></div><div class="stat"><strong>${db.skipped.length}</strong><span class="muted">Im Skip-it-Ordner</span></div></div>`;
}
function showPage(id){
 clearTimeout(exerciseTimer);exerciseTimer=null;exercise=null;
 page=id;
 document.querySelectorAll(".page").forEach(x=>x.classList.toggle("active",x.id===id));
 document.querySelectorAll("nav button").forEach(x=>x.classList.toggle("active",x.dataset.page===id));
 if(id==="today")renderDaily();
 if(id==="learn")renderLearn();
 if(id==="tests")renderTests();
 if(id==="library")renderLibrary();
 if(id==="review")renderReview();
 if(id==="settings")loadSettings();
}
document.querySelectorAll("nav button").forEach(b=>b.addEventListener("click",()=>showPage(b.dataset.page)));

/* -------------------------------------------------------
   TAGESLEKTION
------------------------------------------------------- */
function renderDaily(){
 ensureDaily();
 document.getElementById("todayDate").textContent=new Date().toLocaleDateString("de-DE");
 let words=db.daily.wordIds.map(id=>{
  let found=db.words.find(w=>w.id===id||w.en===id);
  if(found)return found;
  let x=WORD_SEED.find(w=>w[0]===id);
  return x?{id,en:x[0],de:x[1],example:x[2],level:x[3],category:x[4]}:null;
 }).filter(Boolean);
 document.getElementById("dailyWords").innerHTML=words.map((w,i)=>{
  let done=db.daily.learnedWords.includes(w.id);
  return `<div class="word-item"><div class="row"><div><div class="word">${esc(w.en)}</div><div class="translation">${esc(w.de)}</div><p class="example">${esc(w.example)}</p></div><span class="tag">${done?"Gelernt":"Neu"}</span></div><div class="row"><button class="small" onclick="speakText(${JSON.stringify(w.en)})">Anhören</button><button class="small" onclick="saveDailyWord('${esc(w.id)}')">Speichern</button><button class="small" onclick="markDailyLearned('${esc(w.id)}','word')">Als gelernt markieren</button></div></div>`;
 }).join("");
 let sentences=db.daily.sentenceIds.map(id=>SENTENCE_SEED.find(s=>s[0]===id)).filter(Boolean);
 document.getElementById("dailySentences").innerHTML=sentences.map((s,i)=>{
  let done=db.daily.learnedSentences.includes(s[0]);
  return `<div class="word-item"><strong>${i+1}. ${esc(s[0])}</strong><p class="translation">${esc(s[1])}</p><span class="tag">${done?"Gelernt":"Neu"}</span><div class="row"><button class="small" onclick="speakText(${JSON.stringify(s[0])})">Anhören</button><button class="small" onclick="saveDailySentence(${i})">Speichern</button><button class="small" onclick="markDailyLearned('${esc(s[0])}','sentence')">Als gelernt markieren</button></div></div>`;
 }).join("");
}
function saveDailyWord(id){
 let w=WORD_SEED.find(x=>x[0]===id)||db.words.find(x=>x.id===id);
 if(!w)return;
 addWord(w[0]||w.en,w[1]||w.de,w[2]||w.example,"Tageslektion");
}
function saveDailySentence(i){let s=SENTENCE_SEED[i];if(s)addSentence(s[0],s[1],"Tageslektion")}
function markDailyLearned(id,type){
 let arr=type==="word"?db.daily.learnedWords:db.daily.learnedSentences;
 if(!arr.includes(id))arr.push(id);
 save();renderDaily();
}
function startDaily(type){
 ensureDaily();
 let items;
 if(type==="word"){
  items=db.daily.wordIds.map(id=>{
   let old=db.words.find(w=>w.id===id||w.en===id);
   if(old)return old;
   let w=WORD_SEED.find(x=>x[0]===id);
   return w?{id:w[0],en:w[0],de:w[1],example:w[2],level:w[3],category:w[4]}:null;
  }).filter(Boolean);
 }else{
  items=db.daily.sentenceIds.map(id=>{
   let old=db.sentences.find(s=>s.en===id);
   if(old)return old;
   let s=SENTENCE_SEED.find(x=>x[0]===id);
   return s?{id:s[0],en:s[0],de:s[1],level:s[2]}:null;
  }).filter(Boolean);
 }
 startExercise(type,items,"Tageslektion",{daily:true});
}

/* -------------------------------------------------------
   LERNBEREICH
------------------------------------------------------- */
document.querySelectorAll("#learnTabs button").forEach(b=>b.addEventListener("click",()=>setLearnTab(b.dataset.tab)));
function setLearnTab(tab){learnTab=tab;document.querySelectorAll("#learnTabs button").forEach(b=>b.classList.toggle("active",b.dataset.tab===tab));renderLearn()}
function renderLearn(){
 document.querySelectorAll("#learnTabs button").forEach(b=>b.classList.toggle("active",b.dataset.tab===learnTab));
 let box=document.getElementById("learnContent");
 if(learnTab==="translate")box.innerHTML=translateView();
 if(learnTab==="read")box.innerHTML=readView();
 if(learnTab==="speak")box.innerHTML=speakView();
 if(learnTab==="listen")box.innerHTML=listenView();
 if(learnTab==="pictures")box.innerHTML=pictureView();
 if(learnTab==="write")box.innerHTML=writeView();
 if(learnTab==="subtitles")box.innerHTML=subtitleView();
}
function translateView(){return `<div class="card"><h2>Übersetzen</h2><label>Text eingeben</label><textarea id="translationInput" placeholder="Write something in English or German…"></textarea><button class="primary" onclick="translateText()">Übersetzen</button><div id="translationResult"></div><hr><h3>Eigenen Eintrag speichern</h3><label>Englischer Text</label><input id="saveSource" placeholder="English word or sentence"><label>Deutsche Übersetzung</label><input id="saveTarget" placeholder="German translation"><button onclick="saveTranslation()">In Bibliothek speichern</button><p class="notice">Die automatische Übersetzung nutzt einen externen Dienst. Die Qualität und Verfügbarkeit können variieren.</p></div>`}
async function translateText(){
 let input=document.getElementById("translationInput").value.trim();if(!input)return;
 let box=document.getElementById("translationResult");box.innerHTML="Übersetzung wird geladen …";
 let german=/[äöüß]/i.test(input)||/\b(ich|und|der|die|das|nicht|ist|habe|wir|du|sie|ein|eine|mit|für)\b/i.test(input);
 let from=german?"de":"en",to=german?"en":"de";
 try{
  let url="https://api.mymemory.translated.net/get?q="+encodeURIComponent(input)+"&langpair="+from+"|"+to;
  let response=await fetch(url);if(!response.ok)throw Error();
  let json=await response.json(),translated=json.responseData?.translatedText||"";
  box.innerHTML=`<div class="answer"><strong>${esc(translated)}</strong><p class="notice">${from.toUpperCase()} → ${to.toUpperCase()}</p><button onclick="prepareTranslation(${JSON.stringify(input)},${JSON.stringify(translated)})">Zum Speichern übernehmen</button></div>`;
 }catch(e){box.textContent="Die Übersetzung ist gerade nicht verfügbar. Bitte versuche es später erneut."}
}
function prepareTranslation(a,b){document.getElementById("saveSource").value=/[äöüß]/i.test(a)?b:a;document.getElementById("saveTarget").value=/[äöüß]/i.test(a)?a:b}
function saveTranslation(){
 let en=document.getElementById("saveSource").value.trim(),de=document.getElementById("saveTarget").value.trim();
 if(!en||!de)return alert("Bitte beide Felder ausfüllen.");
 if(/[äöüß]/i.test(en)){let x=en;en=de;de=x}
 if(en.split(/\s+/).length>3||/[.!?]/.test(en))addSentence(en,de,"Übersetzung");
 else addWord(en,de,"","Übersetzung");
 alert("Gespeichert.");
}
function readView(){return `<div class="card"><h2>Lesetexte auswählen</h2><label>Thema</label><select id="readCategory"><option value="all">Alle Themen</option>${["Culture","Psychology","Nature","History","Science","Society","Politics","Economy","Travel","Everyday"].map(x=>`<option>${x}</option>`).join("")}</select><label>Sprachniveau</label><select id="readLevel"><option value="all">Alle Niveaus</option><option>A2</option><option>B1</option><option>B2</option><option>C1</option></select><label>Inhaltliche Schwierigkeit</label><select id="readDifficulty"><option value="all">Alle</option><option>Leicht</option><option>Mittel</option><option>Anspruchsvoll</option><option>Sehr anspruchsvoll</option></select><button class="primary" onclick="filterReading()">Texte anzeigen</button><div id="readingResults">${readingCards(db.texts)}</div></div>`}
function readingCards(items){return items.map(t=>`<div class="word-item"><strong>${esc(t.title)}</strong><p class="notice">${esc(t.category||"") } · ${esc(t.level||"")} · ${esc(t.difficulty||"")}</p><button onclick="openReading('${esc(t.id)}')">Text öffnen</button></div>`).join("")||"<div class='empty'>Keine passenden Texte gefunden.</div>"}
function filterReading(){
 let c=document.getElementById("readCategory").value,l=document.getElementById("readLevel").value,d=document.getElementById("readDifficulty").value;
 let items=db.texts.filter(t=>(c==="all"||t.category===c)&&(l==="all"||t.level===l)&&(d==="all"||t.difficulty===d));
 document.getElementById("readingResults").innerHTML=readingCards(items);
}
function openReading(id){
 let t=db.texts.find(x=>x.id===id);if(!t)return;readingText=t;
 if(!db.daily.readTexts.includes(t.id))db.daily.readTexts.push(t.id);
 save();
 let words=(t.words||[]).map(w=>`<span class="tag">${esc(w[0])} – ${esc(w[1])}</span>`).join(" ");
 document.getElementById("learnContent").innerHTML=`<button onclick="renderLearn()">← Zurück zur Auswahl</button><h2>${esc(t.title)}</h2><span class="tag">${esc(t.level)}</span><span class="tag">${esc(t.difficulty)}</span><div class="card"><p>${esc(t.body)}</p><button onclick="speakText(${JSON.stringify(t.body)})">Text anhören</button><hr><button onclick="toggleReadingTranslation()">Deutsche Übersetzung anzeigen</button><div id="readingGerman" class="hidden answer">${esc(t.de||"Für diesen Text ist noch keine deutsche Übersetzung hinterlegt.")}</div><hr><h3>Wörter aus dem Text</h3>${words}<button onclick="saveTextWords('${esc(t.id)}')">Alle Textwörter speichern</button><hr><h3>Übersetzung üben</h3><textarea id="myTranslation" placeholder="Übersetze den Text ins Deutsche …"></textarea><button onclick="saveReadingTranslation('${esc(t.id)}')">Meine Übersetzung speichern</button><hr><h3>Leseverständnis</h3><div id="readingQuestions">${(t.questions||[]).map((q,i)=>`<div class="word-item"><label>${i+1}. ${esc(q[0])}</label><textarea id="readAnswer${i}" placeholder="Answer in English…"></textarea><button onclick="checkReadingAnswer('${esc(t.id)}',${i})">Antwort prüfen</button><div id="readFeedback${i}"></div></div>`).join("")}</div></div>`;
}
function toggleReadingTranslation(){document.getElementById("readingGerman").classList.toggle("hidden")}
function saveTextWords(id){
 let t=db.texts.find(x=>x.id===id);if(!t)return;
 (t.words||[]).forEach(w=>addWord(w[0],w[1],"",t.title));
 alert("Textwörter wurden gespeichert.");
}
function saveReadingTranslation(id){
 let t=db.texts.find(x=>x.id===id),v=document.getElementById("myTranslation").value.trim();if(!t||!v)return;
 db.texts.push({id:uid("translation"),title:"Übersetzung: "+t.title,body:v,de:"",category:"Eigene",level:t.level,difficulty:"Eigene",words:[],questions:[],marked:false});
 save();alert("Deine Übersetzung wurde in der Bibliothek gespeichert.");
}
function checkReadingAnswer(id,i){
 let t=db.texts.find(x=>x.id===id),q=t?.questions?.[i];if(!q)return;
 let answer=document.getElementById("readAnswer"+i).value.trim();
 if(!answer)return alert("Bitte gib eine Antwort ein.");
 let expected=norm(q[1]),actual=norm(answer);
 let words=expected.split(" ").filter(x=>x.length>3);
 let matches=words.filter(x=>actual.includes(x)).length;
 let ok=actual===expected||(words.length>0&&matches>=Math.ceil(words.length*.5));
 document.getElementById("readFeedback"+i).innerHTML=`<div class="feedback ${ok?"good":"bad"}">${ok?"Gute Antwort!":"Vergleiche deine Antwort mit einer möglichen Lösung."}<p>${esc(q[1])}</p></div>`;
 db.history.unshift({type:"reading",id:t.id,correct:ok,at:Date.now()});save();
}
function speakView(){return `<div class="card"><h2>Sprechen & Vorlesen</h2><label>Englischer Übungssatz</label><textarea id="speakInput">I want to improve my English every day.</textarea><div class="row"><button onclick="speakText(document.getElementById('speakInput').value)">Anhören</button><button class="primary" onclick="startSpeechRecognition()">Vorlesen & erkennen</button></div><div id="speechResult" class="answer">Dein erkannter Text erscheint hier.</div><p class="notice">Die Spracherkennung kann Wörter erkennen, ist aber keine professionelle phonetische Aussprachebewertung.</p></div>`}
function startSpeechRecognition(){
 let SR=window.SpeechRecognition||window.webkitSpeechRecognition;
 if(!SR)return alert("Die Spracherkennung wird in diesem Browser nicht unterstützt.");
 let r=new SR();r.lang=db.settings.voice;r.interimResults=false;
 document.getElementById("speechResult").textContent="Ich höre zu …";
 r.onresult=e=>{
  let spoken=e.results[0][0].transcript,target=document.getElementById("speakInput").value;
  document.getElementById("speechResult").innerHTML=`<strong>Erkannt:</strong><p>${esc(spoken)}</p><strong>Übungssatz:</strong><p>${esc(target)}</p><p class="notice">Vergleiche die beiden Texte. Eine genaue Aussprachebewertung ist nicht verfügbar.</p>`;
 };
 r.onerror=()=>document.getElementById("speechResult").textContent="Die Spracherkennung konnte nicht abgeschlossen werden.";
 r.start();
}
function listenView(){return `<div class="card"><h2>Listening practice</h2><p>Höre englische Sätze und versuche, sie zu verstehen. Die Sprachausgabe deines Geräts liest den Text vor.</p><label>Schwierigkeitsgrad</label><select id="listenLevel"><option>A2</option><option selected>B1</option><option>B2</option><option>C1</option></select><button class="primary" onclick="startListening()">Hörübung starten</button></div>`}
function startListening(){
 let level=document.getElementById("listenLevel").value;
 let pool=db.sentences.filter(x=>!x.level||x.level===level);
 if(!pool.length)pool=db.sentences.length?db.sentences:SENTENCE_SEED.map(x=>({en:x[0],de:x[1]}));
 startExercise("listen",shuffle(pool).slice(0,5),"Hörverständnis",{});
}
function pictureView(){return `<div class="card"><h2>Picture vocabulary</h2><p>Visuelle Merkhilfen im Pop-Art-Comic-Stil.</p><div class="grid">${PICTURES.map(p=>`<div class="comic"><div style="font-size:38px">${p[2]}</div><div class="word">${esc(p[0])}</div><div>${esc(p[1])}</div><p style="color:#171614;font-size:13px">${esc(p[3])}</p><button class="small" onclick="speakText(${JSON.stringify(p[0])})">Anhören</button><button class="small" onclick="addWord(${JSON.stringify(p[0])},${JSON.stringify(p[1])},${JSON.stringify(p[3])},'Pictures')">Speichern</button></div>`).join("")}</div></div>`}
function writeView(){return `<div class="card"><h2>Writing practice</h2><label>Aufgabe</label><select id="writingTopic"><option>Describe your day</option><option>Give your opinion</option><option>Describe a difficult decision</option><option>Write an email</option><option>Summarise a text</option></select><textarea id="writingText" placeholder="Write in English …"></textarea><button class="primary" onclick="saveWriting()">Text speichern</button><p class="notice">Der Text wird gespeichert. Eine automatische KI-Korrektur benötigt eine zusätzliche KI-Schnittstelle.</p></div>`}
function saveWriting(){
 let v=document.getElementById("writingText").value.trim();if(!v)return;
 db.texts.push({id:uid("writing"),title:"Schreibübung: "+document.getElementById("writingTopic").value,body:v,de:"",category:"Eigene",level:db.settings.level,difficulty:"Eigene",words:[],questions:[],marked:false});
 save();alert("Dein Text wurde gespeichert.");
}
function subtitleView(){return `<div class="card"><h2>Subtitle practice</h2><label>Übungsmodus</label><select id="subtitleMode"><option>Deutsches Video – englische Untertitel</option><option>Englisches Video – deutsche Untertitel</option><option>Englisches Video – englische Untertitel</option></select><label>Untertiteltext einfügen</label><textarea id="subtitleInput" placeholder="Paste subtitles here …"></textarea><button class="primary" onclick="showSubtitles()">Übung starten</button><div id="subtitleOutput"></div><p class="notice">Diese Version lädt keine Videos oder Untertitel automatisch von Videoplattformen. Du kannst Untertiteltexte hier einfügen.</p></div>`}
function showSubtitles(){
 let txt=document.getElementById("subtitleInput").value.trim();if(!txt)return;
 let lines=txt.split(/\n+/).filter(Boolean);
 document.getElementById("subtitleOutput").innerHTML=lines.map((line,i)=>`<div class="word-item"><strong>${i+1}. ${esc(line)}</strong><button class="small" onclick="speakText(${JSON.stringify(line)})">Anhören</button><button class="small" onclick="addWord(${JSON.stringify(line)} ,'Untertitelzeile','','Untertitel')">Speichern</button></div>`).join("");
}

/* -------------------------------------------------------
   AUDIO
------------------------------------------------------- */
function speakText(text){
 if(!("speechSynthesis" in window))return alert("Audioausgabe wird nicht unterstützt.");
 speechSynthesis.cancel();
 let u=new SpeechSynthesisUtterance(String(text));
 u.lang=db.settings.voice||"en-GB";u.rate=Number(db.settings.rate)||.9;
 speechSynthesis.speak(u);
}

/* -------------------------------------------------------
   WÖRTER UND SÄTZE SPEICHERN
------------------------------------------------------- */
function addWord(en,de,example="",source="Eigene"){
 if(!en||!de)return;
 let old=db.words.find(x=>norm(x.en)===norm(en));
 if(old){old.de=de;if(example)old.example=example;save();return old}
 let x=normaliseEntry({id:uid("word"),en,de,example,source,level:db.settings.level,box:0,due:0,correct:0,wrong:0,marked:false},"word",db.words.length);
 db.words.push(x);save();return x;
}
function addSentence(en,de,source="Eigene"){
 if(!en||!de)return;
 let old=db.sentences.find(x=>norm(x.en)===norm(en));
 if(old){old.de=de;save();return old}
 let x=normaliseEntry({id:uid("sentence"),en,de,source,level:db.settings.level,box:0,due:0,correct:0,wrong:0,marked:false},"sentence",db.sentences.length);
 db.sentences.push(x);save();return x;
}

/* -------------------------------------------------------
   ÜBUNGS-ENGINE
------------------------------------------------------- */
function startExercise(type,items,title,opts={}){
 clearTimeout(exerciseTimer);
 if(!items.length)return alert("Für diese Übung sind keine Einträge vorhanden.");
 exercise={type,items,index:0,title,opts,answered:false,results:[],direction:"en-de",answer:""};
 renderExercise();
}
function currentItem(){return exercise?.items[exercise.index]}
function getItemType(item){return item._type||exercise.type}
function expected(item,dir,type){
 if(type==="listen")return item.de;
 return dir==="en-de"?item.de:item.en;
}
function renderExercise(){
 if(!exercise)return;
 let e=exercise,item=currentItem();
 if(!item){finishExercise();return}
 if(e.type==="grammar"){renderGrammarExercise();return}
 if(e.type==="text"){renderTextExercise();return}
 if(e.type==="listen"){renderListeningExercise();return}
 let type=getItemType(item);
 e.direction=e.opts.direction==="mixed"?(Math.random()<.5?"en-de":"de-en"):(e.opts.direction||"en-de");
 let prompt=e.direction==="en-de"?item.en:item.de;
 let answer=expected(item,e.direction,type);
 let direction=e.direction==="en-de"?"Deutsch":"Englisch";
 document.getElementById("exerciseScreen").classList.remove("hidden");
 document.getElementById("exerciseScreen").innerHTML=`
 <div class="row"><button class="fixed" onclick="exitExercise()">← Beenden</button><span class="tag">${esc(e.title)}</span></div>
 <h1>Aufgabe ${e.index+1} von ${e.items.length}</h1>
 <div class="progress"><span style="width:${pct(e.index,e.items.length)}%"></span></div>
 <div class="card">
  <p class="muted">Übersetze ins ${direction}.</p>
  <div class="exercise-word">${esc(prompt)}</div>
  ${item.example?`<p class="example">${esc(item.example)}</p>`:""}
  <label>Deine Antwort</label>
  <textarea id="exerciseAnswer" ${e.answered?"disabled":""} placeholder="Schreibe deine Übersetzung …">${esc(e.answer)}</textarea>
  ${e.answered?`
   <div class="feedback ${e.correct?"good":"bad"}"><strong>${e.correct?"Richtig!":"Noch nicht richtig."}</strong><p>Mögliche Lösung: ${esc(answer)}</p></div>
   <div class="row"><button class="primary" onclick="nextExercise()">Nächste Aufgabe →</button><button onclick="speakText(${JSON.stringify(prompt)})">Anhören</button></div>
  `:`
   <div class="row"><button class="primary" onclick="checkExerciseAnswer()">Antwort prüfen</button><button onclick="revealExerciseAnswer()">Lösung anzeigen</button><button onclick="skipExerciseItem()">Überspringen</button></div>
  `}
 </div>
 <div class="row"><span class="muted">Richtig: ${e.results.filter(x=>x.correct).length}</span><span class="muted">Falsch: ${e.results.filter(x=>x.correct===false).length}</span></div>
 `;
}
function checkExerciseAnswer(){
 let e=exercise,item=currentItem();if(!e||e.answered)return;
 let input=document.getElementById("exerciseAnswer").value.trim();
 if(!input)return alert("Bitte gib zuerst eine Antwort ein.");
 e.answer=input;
 let type=getItemType(item),solution=expected(item,e.direction,type);
 let variants=String(solution).split(/[;,/]/).map(norm);
 let ok=variants.includes(norm(input));
 if(!ok&&type==="sentence"){
  // Toleranz für Satzzeichen und kleine Unterschiede in der Eingabe.
  let a=norm(input),b=norm(solution);
  ok=a===b;
 }
 recordAnswer(item,type,ok,input);
 e.answered=true;e.correct=ok;e.results.push({id:item.id,correct:ok});
 renderExercise();
 if(db.settings.autoNext)exerciseTimer=setTimeout(()=>{if(exercise&&exercise.answered)nextExercise()},Number(db.settings.autoDelay)*1000);
}
function revealExerciseAnswer(){
 let e=exercise,item=currentItem();if(!e||e.answered)return;
 recordAnswer(item,getItemType(item),false,"");
 e.answered=true;e.correct=false;e.results.push({id:item.id,correct:false});
 renderExercise();
 if(db.settings.autoNext)exerciseTimer=setTimeout(()=>{if(exercise&&exercise.answered)nextExercise()},Number(db.settings.autoDelay)*1000);
}
function recordAnswer(item,type,ok,answer){
 let collection=type==="sentence"?db.sentences:db.words;
 let obj=collection.find(x=>x.id===item.id)||item;
 obj.seen=(obj.seen||0)+1;
 if(ok){
  obj.correct=(obj.correct||0)+1;
  obj.box=Math.min(6,(obj.box||0)+1);
  let intervals=[1,2,4,7,14,30,60];
  obj.due=Date.now()+intervals[obj.box]*86400000;
 }else{
  obj.wrong=(obj.wrong||0)+1;obj.box=0;
  obj.due=Date.now()+10*60*1000;
 }
 if(type==="word"||type==="sentence"){
  let exists=collection.some(x=>x.id===obj.id);
  if(!exists)collection.push(normaliseEntry(obj,type,collection.length));
 }
 db.history.unshift({id:item.id,type,correct:ok,answer,at:Date.now()});
 db.history=db.history.slice(0,1000);
 if(exercise.opts.daily&&ok){
  let key=type==="sentence"?"learnedSentences":"learnedWords";
  let val=type==="sentence"?item.en:item.id;
  if(!db.daily[key].includes(val))db.daily[key].push(val);
 }
 db.quizCount=(db.quizCount||0)+1;save();
}
function skipExerciseItem(){
 let item=currentItem(),type=getItemType(item);
 db.skipped.push({...item,type,skippedAt:Date.now()});
 db.skipped=db.skipped.slice(-500);save();
 exercise.results.push({id:item.id,skipped:true});
 nextExercise();
}
function nextExercise(){
 clearTimeout(exerciseTimer);exerciseTimer=null;
 if(!exercise)return;
 exercise.index++;exercise.answered=false;exercise.answer="";
 renderExercise();
}
function exitExercise(){
 if(!confirm("Übung beenden? Deine bisherigen Antworten bleiben gespeichert."))return;
 clearTimeout(exerciseTimer);exerciseTimer=null;exercise=null;
 document.getElementById("exerciseScreen").classList.add("hidden");
}
function finishExercise(){
 let e=exercise;
 let correct=e.results.filter(x=>x.correct).length;
 let wrong=e.results.filter(x=>x.correct===false).length;
 let skipped=e.results.filter(x=>x.skipped).length;
 document.getElementById("exerciseScreen").innerHTML=`
 <h1>Runde abgeschlossen</h1><div class="card">
 <div class="grid">
 <div class="stat"><strong>${correct}</strong><span class="muted">Richtig</span></div>
 <div class="stat"><strong>${wrong}</strong><span class="muted">Falsch</span></div>
 <div class="stat"><strong>${skipped}</strong><span class="muted">Übersprungen</span></div>
 </div><hr><p>Deine Antworten wurden gespeichert. Falsche Antworten werden früher wiederholt.</p>
 <button class="primary" onclick="closeExerciseTo('review')">Zur Wiederholung</button>
 <button onclick="closeExerciseTo('home')">Zur Startseite</button></div>`;
 exercise=null;
}
function closeExerciseTo(id){document.getElementById("exerciseScreen").classList.add("hidden");showPage(id)}

/* -------------------------------------------------------
   GRAMMATIK UND TESTS
------------------------------------------------------- */
function renderTests(){
 let tabs=Object.keys(GRAMMAR);
 document.getElementById("grammarTabs").innerHTML=tabs.map(x=>`<button class="${x===grammarSelected?"active":""}" onclick="selectGrammar('${esc(x)}')">${esc(x)}</button>`).join("");
 selectGrammar(grammarSelected);
 let total=db.history.filter(x=>x.type==="grammar");
 let correct=total.filter(x=>x.correct).length;
 document.getElementById("testStats").innerHTML=`<div class="grid"><div class="stat"><strong>${total.length}</strong><span class="muted">Grammatikfragen</span></div><div class="stat"><strong>${total.length?pct(correct,total.length):0}%</strong><span class="muted">Trefferquote</span></div></div>`;
}
function selectGrammar(name){
 grammarSelected=name;
 document.getElementById("grammarTabs").innerHTML=Object.keys(GRAMMAR).map(x=>`<button class="${x===name?"active":""}" onclick="selectGrammar('${esc(x)}')">${esc(x)}</button>`).join("");
 let g=GRAMMAR[name];
 document.getElementById("grammarInfo").innerHTML=`<h3>${esc(name)}</h3><p>${esc(g.rule)}</p><p><strong>Beispiele:</strong> ${esc(g.ex)}</p><button class="primary" onclick="startGrammarTopic('${esc(name)}')">Übungen zu diesem Thema</button>`;
}
function startGrammarTopic(name){let g=GRAMMAR[name];startExercise("grammar",shuffle(g.q).map((q,i)=>({id:uid("grammar"),q:q[0],opts:q[1],a:q[2],why:q[3]})),name,{})}
function startChosenTest(){
 let category=document.getElementById("testCategory").value;
 let count=Number(document.getElementById("testCount").value);
 let level=document.getElementById("testLevel").value;
 let items=[],type="word",title="Test";
 if(category==="vocab"){
  items=shuffle(db.words.filter(x=>!x.level||x.level===level));
  if(!items.length)items=shuffle(db.words);
  type="word";title="Vokabeltest";
 }else if(category==="sentences"){
  items=shuffle(db.sentences);type="sentence";title="Satztest";
 }else if(category==="grammar"){
  let all=Object.entries(GRAMMAR).flatMap(([name,g])=>g.q.map(q=>({id:uid("g"),q:q[0],opts:q[1],a:q[2],why:q[3],topic:name})));
  items=shuffle(all);type="grammar";title="Grammatiktest";
 }else if(category==="reading"){
  items=shuffle(db.texts.filter(x=>x.questions?.length)).slice(0,count);
  if(!items.length)return alert("Es sind noch keine Lesetexte mit Fragen vorhanden.");
  type="text";title="Leseverständnis";
 }else{
  items=shuffle([...db.words.map(x=>({...x,_type:"word"})),...db.sentences.map(x=>({...x,_type:"sentence"}))]);
  type="mixed";title="Gemischter Test";
 }
 items=items.slice(0,count);
 if(!items.length)return alert("Bitte füge zuerst Lerninhalte hinzu.");
 startExercise(type,items,title,{direction:"en-de"});
}
function renderGrammarExercise(){
 let e=exercise,q=currentItem();
 document.getElementById("exerciseScreen").classList.remove("hidden");
 document.getElementById("exerciseScreen").innerHTML=`<button onclick="exitExercise()">← Beenden</button><h1>${esc(e.title)}</h1><p>Aufgabe ${e.index+1} von ${e.items.length}</p><div class="progress"><span style="width:${pct(e.index,e.items.length)}%"></span></div><div class="card"><div class="exercise-word">${esc(q.q)}</div><div class="choice">${q.opts.map((o,i)=>`<button onclick="answerGrammar(${i})">${esc(o)}</button>`).join("")}</div><div id="grammarFeedback"></div></div>`;
}
function answerGrammar(index){
 let q=currentItem(),e=exercise;
 let buttons=document.querySelectorAll("#exerciseScreen .choice button");
 buttons.forEach(b=>b.disabled=true);
 let ok=q.opts[index]===q.a;
 db.history.unshift({id:q.id,type:"grammar",correct:ok,at:Date.now()});save();
 e.results.push({correct:ok});e.answered=true;
 document.getElementById("grammarFeedback").innerHTML=`<div class="feedback ${ok?"good":"bad"}">${ok?"Richtig!":"Richtige Antwort: "+esc(q.a)}<p>${esc(q.why)}</p></div><button class="primary" onclick="nextExercise()">Nächste Aufgabe →</button>`;
}
function renderTextExercise(){
 let e=exercise,t=currentItem(),q=t.questions?.[0];
 document.getElementById("exerciseScreen").classList.remove("hidden");
 if(!q){nextExercise();return}
 document.getElementById("exerciseScreen").innerHTML=`<button onclick="exitExercise()">← Beenden</button><h1>${esc(t.title)}</h1><div class="card"><p>${esc(t.body)}</p><label>${esc(q[0])}</label><textarea id="textExerciseAnswer"></textarea><button class="primary" onclick="checkTextExercise()">Antwort prüfen</button><div id="textExerciseFeedback"></div></div>`;
}
function checkTextExercise(){
 let t=currentItem(),q=t.questions[0],a=document.getElementById("textExerciseAnswer").value.trim();
 if(!a)return;
 let expectedWords=norm(q[1]).split(" ").filter(x=>x.length>3);
 let matches=expectedWords.filter(x=>norm(a).includes(x)).length;
 let ok=norm(a)===norm(q[1])||(expectedWords.length&&matches>=Math.ceil(expectedWords.length*.5));
 exercise.results.push({correct:!!ok});
 db.history.unshift({id:t.id,type:"reading",correct:!!ok,at:Date.now()});save();
 document.getElementById("textExerciseFeedback").innerHTML=`<div class="feedback ${ok?"good":"bad"}">${ok?"Gute Antwort!":"Vergleiche deine Antwort mit dieser Lösung."}<p>${esc(q[1])}</p></div><button class="primary" onclick="nextExercise()">Nächste Frage →</button>`;
}
function renderListeningExercise(){
 let e=exercise,item=currentItem();
 document.getElementById("exerciseScreen").classList.remove("hidden");
 document.getElementById("exerciseScreen").innerHTML=`<button onclick="exitExercise()">← Beenden</button><h1>Hörverständnis</h1><p>Aufgabe ${e.index+1} von ${e.items.length}</p><div class="card"><p>Höre dir den englischen Satz an. Übersetze ihn anschließend ins Deutsche.</p><button class="primary" onclick="speakText(${JSON.stringify(item.en)})">▶ Satz anhören</button><textarea id="listenAnswer" placeholder="Deine Übersetzung …"></textarea><button onclick="checkListening()">Antwort prüfen</button><div id="listenFeedback"></div></div>`;
}
function checkListening(){
 let item=currentItem(),answer=document.getElementById("listenAnswer").value.trim();if(!answer)return;
 let ok=norm(answer)===norm(item.de);
 exercise.results.push({correct:ok});
 db.history.unshift({id:item.id,type:"listening",correct:ok,at:Date.now()});save();
 document.getElementById("listenFeedback").innerHTML=`<div class="feedback ${ok?"good":"bad"}">${ok?"Richtig!":"Mögliche Lösung:"}<p>${esc(item.de)}</p></div><button class="primary" onclick="nextExercise()">Nächster Satz →</button>`;
}

/* -------------------------------------------------------
   BIBLIOTHEK
------------------------------------------------------- */
document.querySelectorAll("#libraryTabs button").forEach(b=>b.addEventListener("click",()=>{libraryTab=b.dataset.tab;renderLibrary()}));
function renderLibrary(){
 document.querySelectorAll("#libraryTabs button").forEach(b=>b.classList.toggle("active",b.dataset.tab===libraryTab));
 let q=norm(document.getElementById("librarySearch")?.value||"");
 let items=[];
 if(libraryTab==="words")items=db.words;
 if(libraryTab==="sentences")items=db.sentences;
 if(libraryTab==="texts")items=db.texts;
 if(libraryTab==="marked")items=[...db.words,...db.sentences,...db.texts].filter(x=>x.marked);
 if(libraryTab==="skipped")items=db.skipped;
 items=items.filter(x=>norm((x.en||x.title||"")+" "+(x.de||x.body||"")).includes(q));
 document.getElementById("libraryContent").innerHTML=items.map(x=>libraryItemHTML(x)).join("")||"<div class='empty'>Hier sind noch keine Einträge.</div>";
}
function libraryItemHTML(x){
 let id=esc(x.id),title=x.en||x.title||"",meaning=x.de||x.body||"";
 let buttons=`<button class="small" onclick="toggleMark('${id}')">${x.marked?"★ Markiert":"☆ Markieren"}</button><button class="small" onclick="editEntry('${id}')">Bearbeiten</button>`;
 if(libraryTab==="skipped")buttons+=`<button class="small" onclick="restoreSkipped('${id}')">Wiederherstellen</button>`;
 else buttons+=`<button class="small" onclick="skipEntry('${id}')">Skip it</button>`;
 buttons+=`<button class="small danger" onclick="deleteEntry('${id}')">Löschen</button>`;
 return `<div class="word-item"><strong>${esc(title)}</strong><p class="translation">${esc(meaning)}</p>${x.example?`<p class="example">${esc(x.example)}</p>`:""}<div class="row">${buttons}</div></div>`;
}
function toggleMark(id){
 let x=[...db.words,...db.sentences,...db.texts].find(x=>x.id===id);
 if(x)x.marked=!x.marked;save();renderLibrary();
}
function editEntry(id){
 let x=[...db.words,...db.sentences,...db.texts].find(x=>x.id===id);
 if(!x)return;
 let title=prompt("Englischer Eintrag oder Titel",x.en||x.title||"");
 if(title===null)return;
 let meaning=prompt("Deutsche Übersetzung oder Beschreibung",x.de||x.body||"");
 if(meaning===null)return;
 if("en"in x)x.en=title;else x.title=title;
 if("de"in x)x.de=meaning;else x.body=meaning;
 save();renderLibrary();
}
function deleteEntry(id){
 if(!confirm("Diesen Eintrag wirklich löschen?"))return;
 db.words=db.words.filter(x=>x.id!==id);
 db.sentences=db.sentences.filter(x=>x.id!==id);
 db.texts=db.texts.filter(x=>x.id!==id);
 db.skipped=db.skipped.filter(x=>x.id!==id);
 save();renderLibrary();
}
function skipEntry(id){
 let x=[...db.words,...db.sentences,...db.texts].find(x=>x.id===id);
 if(!x)return;
 if(!db.skipped.some(s=>s.id===id))db.skipped.push({...x,skippedAt:Date.now(),type:db.words.some(w=>w.id===id)?"word":db.sentences.some(s=>s.id===id)?"sentence":"text"});
 save();renderLibrary();
}
function restoreSkipped(id){
 let x=db.skipped.find(x=>x.id===id);if(!x)return;
 let type=x.type;
 if(type==="word"&&!db.words.some(y=>y.id===id))db.words.push(x);
 else if(type==="sentence"&&!db.sentences.some(y=>y.id===id))db.sentences.push(x);
 else if(type==="text"&&!db.texts.some(y=>y.id===id))db.texts.push(x);
 db.skipped=db.skipped.filter(y=>y.id!==id);save();renderLibrary();
}
function addLibraryEntry(){
 let en=prompt("Englisches Wort oder englischer Satz");if(!en)return;
 let de=prompt("Deutsche Übersetzung");if(!de)return;
 if(en.split(/\s+/).length>3||/[.!?]/.test(en))addSentence(en,de);
 else addWord(en,de);
 renderLibrary();
}

/* -------------------------------------------------------
   SMART REVISION / SPACED REPETITION
------------------------------------------------------- */
function duePool(type){
 let now=Date.now();
 let pool=type==="sentence"?db.sentences:type==="all"?[...db.words.map(x=>({...x,_type:"word"})),...db.sentences.map(x=>({...x,_type:"sentence"}))]:db.words;
 let due=pool.filter(x=>!x.due||x.due<=now);
 return due.length?due:pool;
}
function startReview(){
 let type=document.getElementById("reviewType").value;
 let count=document.getElementById("reviewCount").value;
 let direction=document.getElementById("reviewDirection").value;
 let pool=shuffle(duePool(type));
 if(count!=="all")pool=pool.slice(0,Number(count));
 if(!pool.length)return alert("Noch keine passenden Wörter oder Sätze gespeichert.");
 startExercise(type==="all"?"mixed":type,pool,"Smart Revision",{direction});
}
function renderReview(){
 let now=Date.now();
 let dueWords=db.words.filter(x=>!x.due||x.due<=now).length;
 let dueSentences=db.sentences.filter(x=>!x.due||x.due<=now).length;
 document.getElementById("dueStats").innerHTML=`<div class="grid"><div class="stat"><strong>${dueWords}</strong><span class="muted">Fällige Wörter</span></div><div class="stat"><strong>${dueSentences}</strong><span class="muted">Fällige Sätze</span></div></div>`;
 document.getElementById("recentHistory").innerHTML=db.history.slice(0,10).map(x=>`<div class="word-item"><span>${x.correct===true?"✓":x.correct===false?"✕":"–"}</span> <span class="muted">${new Date(x.at).toLocaleString("de-DE")}</span><span class="tag">${esc(x.type)}</span></div>`).join("")||"<p class='muted'>Noch keine Antworten gespeichert.</p>";
}

/* -------------------------------------------------------
   EINSTELLUNGEN
------------------------------------------------------- */
function loadSettings(){
 document.getElementById("autoNext").value=String(db.settings.autoNext);
 document.getElementById("autoDelay").value=String(db.settings.autoDelay);
 document.getElementById("defaultLevel").value=db.settings.level;
 document.getElementById("voice").value=db.settings.voice;
 document.getElementById("speechRate").value=db.settings.rate;
}
function saveSettings(){
 db.settings.autoNext=document.getElementById("autoNext").value==="true";
 db.settings.autoDelay=Number(document.getElementById("autoDelay").value);
 db.settings.level=document.getElementById("defaultLevel").value;
 db.settings.voice=document.getElementById("voice").value;
 db.settings.rate=Number(document.getElementById("speechRate").value);
 save();alert("Einstellungen gespeichert.");
}
function exportData(){
 let blob=new Blob([JSON.stringify(db,null,2)],{type:"application/json"});
 let url=URL.createObjectURL(blob),a=document.createElement("a");
 a.href=url;a.download="go-on-backup.json";a.click();URL.revokeObjectURL(url);
}
function importData(event){
 let file=event.target.files?.[0];if(!file)return;
 let reader=new FileReader();
 reader.onload=()=>{
  try{
   let imported=JSON.parse(reader.result);
   if(!Array.isArray(imported.words)||!Array.isArray(imported.sentences))throw Error();
   db={...freshData(),...imported};
   db.settings={...freshData().settings,...(imported.settings||{})};
   db.daily={...freshData().daily,...(imported.daily||{})};
   save();alert("Backup erfolgreich importiert.");showPage("library");
  }catch(e){alert("Die Datei konnte nicht importiert werden. Bitte prüfe, ob es ein go on-Backup ist.")}
 };
 reader.readAsText(file);
}
function resetData(){
 if(!confirm("Möchtest du wirklich alle gespeicherten Lerninhalte löschen?"))return;
 localStorage.removeItem(STORAGE_KEY);db=freshData();save();location.reload();
}

/* -------------------------------------------------------
   INITIALISIERUNG
------------------------------------------------------- */
function purgeSkipped(){
 let cutoff=Date.now()-10*86400000;
 db.skipped=db.skipped.filter(x=>(x.skippedAt||Date.now())>cutoff);
}
function initialise(){
 purgeSkipped();
 ensureDaily();
 // Vorhandene Standardtexte in der Bibliothek ergänzen.
 TEXTS.forEach(t=>{if(!db.texts.some(x=>x.id===t.id))db.texts.push({...t,marked:false})});
 save();
 renderDaily();
 updateHome();
 renderLearn();
 renderTests();
 renderLibrary();
 renderReview();
}
initialise();
</script>
</body>
</html>
