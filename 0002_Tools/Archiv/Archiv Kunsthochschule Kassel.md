Die Kunsthochschule Kassel produziert, als Institution künstlerisch und gestalterischer Bildung, seid ihrem bestehen Wissen und künstlerisch/gestalterische Arbeiten. Über die letzten Jahre wurden von verschiedenen Akteur`*`innen der Hochschule an der Idee eines öffentlich zugänglichem Archives gearbeitet. 
Es gab unter anderem eine Ausstellung zur Geschichte des Gebäudes und dessen Architekten Paul Posenenske, sowie Forschungsprojekte zur Geschichte der Kunsthochschule. 
"Die Kunstwissenschaft ermittelt: Die Kunsthochschule in fünf Jahrzehnten (1910–1960) "
https://kunsthochschulekassel.de/willkommen/news/die-kunstwissenschaft-ermittelt-die-kunsthochschule-in-fuenf-jahrzehnten-1910-1960.html
## Darstellung des Studienganges Viskom an der KHK
Konzept und visuelle Umsetzung von [Hendrik Dorgarthen](https://kunsthochschulekassel.de/en/people/dorgathen-hendrik.html) 

![[ViskomStrukWS2021_22 1.jpeg]]
## Darstellung von Gedankengängen und Konzepten zum Viskom Archiv
Konzept und visuelle Umsetzung von [Hendrik Dorgarthen](https://kunsthochschulekassel.de/en/people/dorgathen-hendrik.html) 

![[Mindmap_Viskom_Archiv01.jpg]]


# Archiv-Website Kunsthochschule Kassel - für Studenten/Lehrende – Events, Werke, Vorlesungen

![[Archivplan.svg]]
Das hier gezeigte Diagramm veranschaulicht eine mögliche Implementierung eines Archivkonzeptes für die Kunsthochschule Kassel.
Das Konzept geht davon aus, dass die Kunstwerke und Dokumentationen der Studierenden und Lehrenden systematisch erfasst, kategorisiert und zugänglich gemacht werden. Das Archiv soll als zentrale Anlaufstelle für die Sammlung, Bewahrung und Präsentation künstlerischer und gestallterischer Arbeiten dienen.

Im Kern beruht das Konzept auf mehreren grundlegenden Prinzipien:

1. **Digitale Erfassung und Speicherung**: 
	Alle Kunstwerke und relevanten Dokumentationen werden digital erfasst und in einer zentralen Datenbank gespeichert. Dies ermöglicht eine effiziente Verwaltung und Langzeitarchivierung der Daten.

3. **Kategorisierung und Metadaten**: 
	Jedes Werk wird detailliert kategorisiert und mit Metadaten versehen, um eine präzise Suche zu gewährleisten. Diese Metadaten umfassen Informationen wie Titel, Künstler, Entstehungsdatum, Medium, sowie thematische Schlagworte.

1. **Headless-Datenbank-Architektur**: 
	Ein zentraler Aspekt dieses Konzepts ist der "headless" - Charakter der Datenbank. Dies bedeutet, dass die Datenbank unabhängig von der visuellen und interaktiven Gestaltung der Benutzeroberflächen agiert. Die Datenbank stellt über APIs (Application Programming Interfaces) die notwendigen Daten zur Verfügung, sodass verschiedene Frontend-Lösungen entwickelt und integriert werden können. Dies ermöglicht eine hohe Flexibilität bei der Gestaltung von Nutzeroberflächen, die an unterschiedliche Anforderungen angepasst werden können.

4. **Zugänglichkeit und Nutzerfreundlichkeit**:
	Das Archiv wird über eine nutzerfreundliche Online-Plattform zugänglich gemacht. Studierende, Lehrende und externe Interessierte können über verschiedene Suchfunktionen auf die Werke zugreifen. Dank der headless-Architektur können diese Plattformen individuell gestaltet werden, ohne die Datenintegrität zu gefährden.

6. **Sicherheits- und Backup-Maßnahmen**: 
	Um die langfristige Erhaltung der digitalen Dateien zu gewährleisten, werden regelmäßige Backups und Sicherheitsmaßnahmen implementiert. Dies schützt die Daten vor Verlust und unbefugtem Zugriff.

8. **Kollaborative Elemente**: 
	Das Archivkonzept fördert die Zusammenarbeit zwischen verschiedenen Abteilungen und Projekten innerhalb der Kunsthochschule. Es schafft eine Plattform für den Austausch von Wissen und Ressourcen, um die kreative Entwicklung/Bildung zu unterstützen.

10. **Interoperabilität**: 
	Durch eine sorgfältige Gestaltung und Dokumentation der Datenstruktur und Schnittstellen wird sichergestellt, dass das Archivsystem mit anderen Systemen und Plattformen nahtlos zusammenarbeiten kann. Dies ermöglicht es, Daten zwischen verschiedenen Institutionen auszutauschen, gemeinsame Projekte zu realisieren und die Integration mit externen Datenquellen oder Archiven zu erleichtern. Standardisierte Protokolle und Formate, wie beispielsweise RESTful APIs, gewährleisten eine hohe Kompatibilität und Flexibilität, wodurch das Archivsystem zukunftssicher und erweiterbar bleibt.

12. **Datenintegrität**: 
	Die eingespeisten Daten müssen den wissenschaftlichen und künstlerischen Standards genügen, um die Qualität und Verlässlichkeit des Archivs sicherzustellen. Dies umfasst mehrere Aspekte:

    - **Genauigkeit und Vollständigkeit**: 
	    Alle Datensätze müssen präzise und umfassend erfasst werden. Dies bedeutet, dass alle relevanten Informationen wie Titel, Künstler, Entstehungsdatum, Medium, und thematische Schlagworte vollständig und korrekt eingegeben werden.
    
    - **Verifikation und Validierung**: 
	    Eingabedaten sollten einer gründlichen Verifikation und Validierung unterzogen werden. Dies kann durch Peer-Reviews, Überprüfung durch Fachexperten oder durch automatische Validierungsmechanismen erfolgen.
	
    - **Qualitätsstandards**:
	    Es sollten klare Richtlinien und Standards für die Datenerfassung und -eingabe definiert werden. Diese Standards sollten regelmäßig überprüft und aktualisiert werden, um den aktuellen wissenschaftlichen und künstlerischen Anforderungen zu entsprechen.
    
    - **Versionierung und Nachvollziehbarkeit**:
	    Jede Änderung an den Datensätzen sollte versioniert und dokumentiert werden, um eine vollständige Nachvollziehbarkeit zu gewährleisten. Dies bedeutet, dass jede Änderung, der Zeitpunkt der Änderung und die verantwortliche Person oder Institution festgehalten werden.
    
    - **Sicherheit und Schutz vor Manipulation**: 
		Um die Integrität der Daten zu gewährleisten, müssen, wie oben beschrieben, Sicherheitsmaßnahmen implementiert werden, die vor unbefugtem Zugriff und Manipulation schützen. Dies umfasst sowohl technische Maßnahmen wie Verschlüsselung und Zugriffsrechte als auch organisatorische Maßnahmen wie regelmäßige Audits und Überprüfungen.

Ein Beispiel für eine solche Plattform ist die Software [[Madek]], die von der Hochschule für Gestalltung Karlsruhe, in Kooperation mit der Zürcher Hochschule der Künste entwickelt wird.

Für den wissenschaftlichen Wert und die Erhöhung der internationalen Sichtbarkeit ist die Integration von [[DOI]]s für bestimmte Daten in der Datenbank sinnvoll. Durch diese Maßnahme wird die Nachvollziehbarkeit und Zitationsfähigkeit der archivierten Werke und Forschungsergebnisse verbessert. Dies steigert auch deren internationale Sichtbarkeit und wissenschaftliche Anerkennung.
# Film und Bewegtbild-Archiv an der Kunsthochschule

Anknüpfend an die oben skizzierte Konzept könnte die Datenbank auch eine Möglichkeit schaffen, Abschlussfilme zu finden und zu sichten. Eine eventuelle Integrationsmöglichkeit ließe das Filmarchiv der Universität Kassel zu. https://filmarchiv.uni-kassel.de/
# Technik 
Für das Erfassen und die Speicherung von Daten ist eine konsistente Datenstruktur von Nöten. Je nach dem welche Zwecke und Datenmengen erwartet werden, eignen sich verschiedene Datenbankkonzepte für die Archivdatenbank. 
Neben SQL-Datenbanken (z.B.[[MySQL]]), können auch NOSQL-Datenbanken (e.g.[[mongoDB]]) und POSTGRES-Datenbanken (z.B. [[PostgreSQL]])genutzt werden. Ergänzend gibt es Softwarepakete, die weitere Funktionen, wie Nutzerauthentifizierung oder S3 Storagebuckets mitliefern (z.B.[[Supabase]]). 