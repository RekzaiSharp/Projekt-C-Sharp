# Lessons Learned

### <u>1. Frühzeitige Recherchephase einplanen</u>

Für weitere Projekte, in denen das Team mit ihnen unbekannten Technologien und Tools arbeitet, muss eine vorzeitige Recherchephase eingeplant werden, bevor mit der eigentlichen Entwicklung begonnen wird. Obwohl dies angesichts der knappen Zeit und dem guten Projektfortschritt in der Anfangszeit als unnötig angesehen wurde, stellte sich dies als nötiges Mittel heraus, um nicht nur einen groben Überblick und eine gute Dokumentation zu erhalten, sondern auch, damit jedes Teammitglied eine grundlegende Kompetenz in einem Tool oder einer Pipeline-Stage vorweisen kann.

## <u>2. Arbeitspakete klein halten</u>

In den ersten beiden Sprints waren die Arbeitspakete in zu große, allgemein gehaltene Tasks gegliedert. Dadurch ist die Produktivität des Teams in der sehr wichtigen Frühphase des Projekts stark reduziert. Nach dieser Erkenntnis wurden die Tasks in kleinere Untertasks aufgeteilt, deren Bearbeitung maximal 30 Minuten in Anspruch nehmen dürfte. Für weitere Projekte sollte die Aufteilung der Arbeitspakete bereits im ersten Sprint klein genug gewählt werden.

### <u>3. Arbeitsergebnisse und Erkenntnisse dokumentieren</u>

Um zu garantieren, dass das Team von den Rechercheergebnissen und Erkenntnissen der einzelnen Teammitglieder profitieren kann, muss jeder Entwickler diese zeitnah dokumentieren. Dies verhindert außerdem, dass durch den zeitlichen Abstand zwischen Implementierung und Dokumentation der Entwickler Details vergisst.
Die Dokumentation eines Tools oder eines Pipeline-Jobs wurde im Nachhinein als Einzeltasks in Jira eingefügt. Darauf gilt es bei zukünftigen Projekten von Anfang an zu achten.

## <u>4. Pair Programming durchführen</u>

Zur Projektmitte hin divergierte der Kenntnisstand der einzelnen Teammitglieder stark. Während manche Entwickler ein hohes Grad an Wissen erarbeitet haben, waren andere wieder gehemmt, an der CI/CD-Pipeline zu arbeiten und weitere Jobs und Stages zu implementieren.
Ein guter Rat wurde ab dem 3. Sprint umgesetzt: das Team hat sich selbstständig zu Pair-Programming-Sessions getroffen und so nicht nur eine höhere Produktivität erreicht, sondern so auch ihr Wissen direkt weitergegeben.

## <u>5. Kommunikation</u>
Für ein erfolgreiches Projekt ist es unverzichtbar, dass jedes Teammitglied seine Arbeitspakete bearbeitet und rechzeitig zu Kundenterminen (Sprint Review) bearbeitet und vorbereitet hat. Natürlich gibt es immer wieder Dinge, die das Team von der Arbeit am Projekt abhalten können, seien es Abgaben für das Studium, Arbeit, private Verpflichtungen oder Krankheit. Wichtig hierbei ist es, das Team rechtzeitig über Impediments zu informieren, damit beispielsweise Arbeitspakete neu verteilt werden können. Hierbei ist es wichtig, dem Team die Hemmungen zu nehmen, dies zu kommunizieren.

## <u>6. Restriktiven Workflow implementieren</u>

In den ersten beiden Sprints wurden Aufgaben in Jira nur unzureichend geführt. So kam es zu unzureichend bearbeiteten Aufgaben, die bereits fertig abgenommen wurden, der doppelten Bearbeitung einzelner Aufgaben und generell einen fehlenden Überblick des gesamten Projektteams über den Arbeitsfortschritt.

Daraufhin wurde ein restriktiverer Workflow des Jira-Projekts eingeführt: 
- Jeder Task im Sprint Backlog musste im Sprint Planning einem Teammitglied zugewiesen sein. Das Sprint Planning durfte, anders als in den vorherigen Sprints, nicht vorzeitig abgeschlossen werden!
- Der Status eines Tasks konnte nur vom ihm zugewiesenen Entwickler geändert werden. Bei Freigabe erfolgte eine Abnahme nur durch den Product Owner.
- Es mussten zwei Checks durch andere Entwickler erfolgen, die bei Bedarf den Status wieder zurücksetzen konnten, falls das Ergebnis ihrer Meinung nach den Anforderungen nicht entsprach. Somit war zudem gewährleistet, dass mindestens zwei Teammitglieder sich mit der Aufgabe auseinandergesetzt haben.

