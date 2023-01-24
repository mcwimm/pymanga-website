---
title: "Erste Anwendungen von pyMANGA"
linkTitle: "Erste Anwendungen von pyMANGA"
weight: 2
description:
---

<head>
<style type="text/css">
<!--
details summary {color: white; background: #00305E; margin-bottom: 1em;}
-->
</style>
</head>

Bevor Sie mit den ersten Anwendungen beginnen, sollten Sie, falls noch nicht geschehen, die <a href="/de/docs/erste_schritte/installation">Anleitungen zur Installation und Vorbereitung</a> für ihr entsprechendes Betriebssystem lesen.
Diese wird vor allem für Anfänger empfohlen, welche wenig Erfahrung mit **Python** und der Eingabekonsole haben.
Diese Anleitung ist grundsätzlich für alle drei Betriebsyteme (MacOS, Unbunt, Windows) geeignet.
Der nachfolgende Absatz ist basierend auf der Ausführung in Windows beschrieben.
Sollten Sie z.B. Ubuntu verwenden, beachten Sie bitte die Übertragung von allgemein bekannten Unterschieden (z.B. die Verwendung von Backslashes)

## Einfachere Beispiel-Setups ohne OpenGeoSys

Zunächst muss wieder mit der Konsolenoberfläche zu dem Dateispeicherort der **pyMANGA** Hauptebene navigiert werden.
Durch die Eingabe von 

	• py -3.7 main.py -h  			         [1a]

für Windows und

	• python3 main.py -h  			         [1b]

für Ubuntu wird **pyMANGA** gestartet und alle verfügbaren Eingabeoptionen ausgegeben (-h steht für help).

<figure>
<a name="Abbildung_1"></a>
<img src="/pictures/getting_started/first_applications_of_pymanga/running_pymanga.jpg">
<figcaption><font size = "1"><i><b>Abbildung 1:</b> Ausgeführte main.py Datei in der Windows-Eingabekonsole.</i></font></figcaption>
</figure><p>

Hier ist zu sehen, dass die ***main.py*** Datei ausgeführt wurde und auf weitere Eingaben wartet.
Damit ist der Start von **MANGA** geglückt und Sie können ein paar erste Verwendungsbeispiele testen.
Dazu können Sie folgenden Code eingeben (siehe <a href="/de/docs/erste_schritte/erste_anwendungen_von_pymanga/#Abbildung_2">Abbildung 2</a>).

	• py -3.7 main.py -i test\SmallTests\Test_Setups_small\AllSimple_WithOutput.xml			  [2]

***-i*** beschreibt dabei den Index bzw. den Pfad der Datei, in der der Input definiert ist, der für dieses Beispiel verwendet werden soll.
Beachten Sie, dass die Verwendung von Bachslashes im Dateipfad nur für die Windows-Variante gilt. 

<figure>
<a name="Abbildung_2"></a>
<img src="/pictures/getting_started/first_applications_of_pymanga/error_output.jpg">
<figcaption><font size = "1"><i><b>Abbildung 2:</b> Fehlermeldung beim Auführen von <b>py main.py -i .\test\SmallTests\Test_Setups_small\AllSimple_WithOutput.xml.</b></i></font></figcaption>
</figure><p>

Nach Ausführung des Codes wird eine Fehlermeldung ausgegeben, welche beschreibt, dass ein Ordner Namens ***testoutputs*** nicht existiert, welcher aber vom Programm benötigt wird, um die erzeugten Daten der Simulation abzuspeichern.
Diese Information findet sich in der Datei ***AllSimple_WithOutput.xml***, welche den Input für unser Beispiel definiert.
Um diese einsehen zu können, müssen Sie die Datei mit Hilfe des Editors öffnen.
Die XML-Datei finden Sie unter folgendem Dateifpad:

***test\SmallTests\Test_Setups_small\AllSimple_WithOutput.xml***


Dazu erstellen Sie bitte das Verzeichnis, welches als output_dir (Output-Directory) im Projekt-File angegeben ist. Die Standardeinstellung lautet:

***test\testoutputs***


Der angegebene Dateipfad ist relativ zu dem Ordner, in dem sie **pyMANGA** gestarten haben, angegeben (siehe <a href="/de/docs/erste_schritte/erste_anwendungen_von_pymanga/#Abbildung_3">Abbildung 3</a>).
Dazu folgen Sie dem in <a href="/de/docs/erste_schritte/erste_anwendungen_von_pymanga/#Abbildung_2">Abbildung 2</a> angegeben Dateipfad im Ordner ***pyMANGA-master*** und machen einen **Rechtsklick** auf die genannte Datei, gehen auf ***Öffnen mit*** und suchen den Editor raus (siehe <a href="/de/docs/erste_schritte/erste_anwendungen_von_pymanga/#Abbildung_3">Abbildung 3</a>).

<figure>
<a name="Abbildung_3"></a>
<img src="/pictures/getting_started/first_applications_of_pymanga/control_file.jpg">
<figcaption><font size = "1"><i><b>Abbildung 3:</b> Inhalt von </b>AllSimple_WithOutput.xml</b>, geöffnet mit dem Text Editor.</i></font></figcaption>
</figure><p>

In der Datei finden sich die **rot-markierten** Zeilen, welche angeben was vom Programm ausgegeben werden soll, z.B. die **Baumhöhe** **(h_stem)** und wo hin, nämlich in den nicht existenten Ordner ***testoutputs***, welcher als Ausgabeort für die Simulationsergebnisse definiert wurde.
Demzufolge müssen Sie nun diesen Ordner erstellen.
Dazu machen Sie einen **Rechtsklick** in den Unterordner ***C:\Users\chris\Desktop\pyMANGA-master\test***, klicken auf Neuen Ordner erstellen und nennen ihn testoutputs (siehe <a href="/de/docs/erste_schritte/erste_anwendungen_von_pymanga/#Abbildung_4">Abbildung 4</a>).

<figure>
<a name="Abbildung_4"></a>
<img src="/pictures/getting_started/first_applications_of_pymanga/create_output_folder.jpg">
<figcaption><font size = "1"><i><b>Abbildung 4:</b> Erstellung des neuen Ordners <b>testoutputst</b>.</i></font></figcaption>
</figure><p>

Im Anschluss führen Sie den Code 1 erneut in der Eingabeaufforderung aus.
Nun sollte das Programm die erste Simulation starten (siehe <a href="/de/docs/erste_schritte/erste_anwendungen_von_pymanga/#Abbildung_5">Abbildung 5</a>).
Es gibt verschiedene input Parameter, welche in <b>MANGA</b> Projektkonfigurationen eingestellt werden können.
Die Datei, welche soeben gestartet wurde ist eine Konfigurationsdatei.
Eine Beschreibung dieser Parameter findet sich auf der folgenden [Homepage](https://jbathmann.github.io/pyMANGA/project_dox__MangaProject__MangaProject.html "https://jbathmann.github.io/pyMANGA/project_dox__MangaProject__MangaProject.html").
Die Ergebnisse der Simulation werden einmal visuell in einem separaten Fenster dargestellt (siehe <a href="/de/docs/erste_schritte/erste_anwendungen_von_pymanga/#Abbildung_6">Abbildung 6</a>) und in Form von ***csv*** Dateien im neu angelegten Ordner ***testoutputs***.
Damit haben Sie erfolgreich das erste Beispiel ausgeführt.

<figure>
<a name="Abbildung_5"></a>
<img src="/pictures/getting_started/first_applications_of_pymanga/running_pymanga_output_exists.jpg">
<figcaption><font size = "1"><i><b>Abbildung 5:</b> Widerholte Auführung von  <b>py main.py -i ProjectLib\ExampleSetups\AllSimple_WithOutput.xmlt</b> nach Erstellung des neuen Ordners <b>testoutputs</b>.</i></font></figcaption>
</figure><p>

<figure>
<a name="Abbildung_6"></a>
<img src="/pictures/getting_started/first_applications_of_pymanga/results_matplotlib.jpg">
<figcaption><font size = "1"><i><b>Abbildung 6:</b> Visuelle Ergebnisse der Simulation.</i></font></figcaption>
</figure><p>

Analog dazu können Sie mit den folgenden Codes zwei weitere Beispiele ausprobieren, in dem andere Input-Varianten definiert sind.
Dazu müssen Sie aber zunächst den Ordner ***testoutputs*** leeren bzw. einen anderen Ordner in den Input-Dateien mit Hilfe des Editors definieren, da das Programm die alten Output-Daten nicht überschreiben kann.
Anschließend geben Sie wieder den Code in die Eingabeaufforderung ein.
Des Weiteren wurden wiederum andere Parameter verändern.
Verschaffen Sie sich mit Hilfe der [Homepage](https://jbathmann.github.io/pyMANGA/project_dox__MangaProject__MangaProject.html "https://jbathmann.github.io/pyMANGA/project_dox__MangaProject__MangaProject.html") einen Überblick über die Einstellungsvarianten der Input-Parameter, die in den Beispielen verwendet werden und vergleichen Sie sie.


	• py -3.7 main.py -i test\SmallTests\Test_Setups_small\FIXEDSAL_BETTINA.xml 			 [3] 
	• py -3.7 main.py -i test\SmallTests\Test_Setups_small\FON_SAZOI_KIWI.xml			 [4]

Aufgrund von anderen Projekt-Konfigurationen (in ***FIXEDSAL_BETTINA.xml und FON_SAZOI_KIWI.xml***) wird unteranderem im Beispiel zu Code 3 keine visuelle Darstellung ausgegeben (vergleiche <a href="/de/docs/erste_schritte/erste_anwendungen_von_pymanga/#Abbildung_6">Abbildung 6</a>).

## Komplexere Beispiel-Setups mit OpenGeoSys


Die nächste Anwendung von **pyMANGA** nutzt <a href="https://www.opengeosys.org/">**OpenGeoSys**</a> (OGS).
Dabei handelt es sich um ein wissenschaftliches Open-Source-Projekt zur Entwicklung numerischer Methoden für die Simulation von thermo-hydro-mechanisch-chemischen (THMC) Prozessen in porösen und fragmentierten Medien.
Um **OGS** zu nutzen müssen Sie dieses zunächst herunterladen und installieren.
Da die Installation zwischen den Betriebssystemen sehr verschieden ist, ist nachfolgende Erklägung individuell für Ihr Betriebssystem formuliert.


<details>
<summary >Erste Anwendungen in Ubuntu</summary>
<p>

Auf dieser <a href="https://github.com/ufz/ogs/releases/tag/6.2.2">Homepage</a> finden Sie am Seitenende mehrere Varianten der OGS-Version 6.2.2.
Wählen Sie die Variante **"ogs-6.2.2-Linux-5.3.4-arch1-1-ARCH-x64-python--de-utils"** aus und laden Sie den komprimierten Ordner herunter oder benutzen Sie direkt diesen [Link](https://github.com/ufz/ogs/releases/download/6.2.2/ogs-6.2.2-Linux-5.3.4-arch1-1-ARCH-x64-python-de-utils.tar.gz).
**Stellen Sie bitte sicher, dass Sie exakt diese Version von OGS downloaden.**

Entpacken Sie den Ordner und verschieben Sie die drei in diesem enthaltene Ordner (_bin_, _lib_ und _share_) ausgehend von der pyMANGA-Hauptebene in folgenden Ordner:

	./TreeModelLib/BelowgroundCompetition/OGS

Die Dateien müssen direkt in diesem Ordner liegen.
Um zu überprüfen ob OGS auf Ihrem Rechner ausführbar ist, öffnen Sie ein Terminal in der **pyMANGA**-Hauptebene und geben Sie folgendes ein:

	./TreeModelLib/BelowgroundCompetition/OGS/bin/ogs

Lässt sich OGS korrekt ausführen, erhalten Sie folgende Ausgabe:




	PARSE ERROR:
	             Required argument missing: project-file

	Brief USAGE: 
	   ./ogs  [--enable-fpe] [--unbuffered-std-out]
	          [--config-warnings-nonfatal] [-l <LOG_LEVEL>] [-o <PATH>] [-r
	          <PATH>] [--] [--version] [-h] <PROJECT_FILE>

Sollte das nicht funktionieren, überprüfen Sie zunächst ob sie das Python-Modul "vtk" in der Version 8.1.2 installiert haben.
Lesen Sie hierzu auch den <a href="/de/docs/erste_schritte/installation#Installation_Ubuntu">Abschnitt zur Installation von pyMANGA in Ubuntu</a>.
Wenn Sie an dieser Stelle auf unüberwindbare Probleme stoßen <a href="/de/impressum">kontaktieren</a> Sie uns.


Nun können Sie das nächste Anwendungsbeispiel starten, indem Sie ein Terminal in der **pyMANGA**-Hauptebene öffnen und nachfolgenden Befehl eingeben:

	python3 main.py -i test/LargeTests/Test_Setups_large/OGS3D_SAZOI_BETTINA.xml 


</p>
</details>

<details>
<summary>Erste Anwendungen in Windows</summary>
<p>

Um **OGS** zu installieren gehen Sie auf die folgende [Homepage](https://www.opengeosys.org/releases/ "https://www.opengeosys.org/releases/")  und scrollen bis Sie die **Version** **6.3.0** finden und downloaden diese (siehe <a href="/de/docs/erste_schritte/erste_anwendungen_von_pymanga/#Abbildung_7">Abbildung 7</a> und <a href="/de/docs/erste_schritte/erste_anwendungen_von_pymanga/#Abbildung_8">Abbildung 8</a>).


<figure>
<a name="Abbildung_7"></a>
<img src="/pictures/getting_started/first_applications_of_pymanga/download_ogs_windows.jpg">
<figcaption><font size = "1"><i><b>Abbildung 7:</b> Versionsauswahl von <b>OGS</b>.</i></font></figcaption>
</figure><p>

<figure>
<a name="Abbildung_8"></a>
<img src="/pictures/getting_started/first_applications_of_pymanga/Download_von_OGS 6.3.0.jpg">
<figcaption><font size = "1"><i><b>Abbildung 8:</b> Download von OGS 6.3.0.</i></font></figcaption>
</figure><p>

Wählen Sie, entsprechend ihres Betriebssystems, die zu downloadende Datei aus.
Anschließend entpacken Sie die Zip Datei, kopieren den ***Bin*** Ordner und fügen diese in den ***pyMANGA-master*** Ordner in den folgenden Pfad ein (siehe <a href="/de/docs/erste_schritte/erste_anwendungen_von_pymanga/#Abbildung_9">Abbildung 9</a>).

	\pyMANGA-master\TreeModelLib\BelowgroundCompetition\OGS					 [5]

<figure>
<a name="Abbildung_9"></a>
<img src="/pictures/getting_started/first_applications_of_pymanga/ogs_path.jpg">
<figcaption><font size = "1"><i><b>Abbildung 9:</b> Einfügen von OGS in den pyMANGA-master Ordner.</i></font></figcaption>
</figure><p>

Damit ist **OGS** installiert.
Um zu testen ob es ordnungsgemäß funktioniert, öffnen Sie den ***Bin*** Ordner, drücken **shift** und die **rechte** Maustaste und wählen **PowerShell-Fenster** **hier** **öffnen** (siehe <a href="/de/docs/erste_schritte/erste_anwendungen_von_pymanga/#Abbildung_10">Abbildung 10</a>).

<figure>
<a name="Abbildung_10"></a>
<img src="/pictures/getting_started/first_applications_of_pymanga/ogs_powershell.jpg">
<figcaption><font size = "1"><i><b>Abbildung 10:</b> Öffnen eines PowerShell-Terminals</i></font></figcaption>
</figure><p>

Kopieren Sie den Pfad, der im **PowerShell-Fenster** angezeigt wird, und hängen Sie ***\OGS*** an und führen dies mit der **Eingabetaste** aus.
In der folgenden <a href="/de/docs/erste_schritte/erste_anwendungen_von_pymanga/#Abbildung_11">Abbildung 11</a> sehen Sie die Ausgabe des **PowerShell-Fensters**, wenn **OGS** reibungslos funktioniert. 

<figure>
<a name="Abbildung_11"></a>
<img src="/pictures/getting_started/first_applications_of_pymanga/output_ogs_runs.jpg">
<figcaption><font size = "1"><i><b> Abbildung 11:</b> Ausgabe bei Ordnungsgemäßer Funktion von OGS.</i></font></figcaption>
</figure><p>

Nun können Sie das nächste Anwendungsbeispiel starten, indem Sie wie gehabt die Eingabeaufforderung im ***pyMANGA-master*** Ordner öffnen und pyMANGA starten.
Anschließend geben Sie den nachfolgenden Befehl ein (siehe <a href="/de/docs/erste_schritte/erste_anwendungen_von_pymanga/#Abbildung_12">Abbildung 12</a>).

	py -3.7 main.py -i test\LargeTests\Test_Setups_large\OGS3D_SAZOI_BETTINA.xml 				 [6]

<figure>
<a name="Abbildung_12"></a>
<img src="/pictures/getting_started/first_applications_of_pymanga/run_ogs_sample_setup.jpg">
<figcaption><font size = "1"><i><b>Abbildung 12:</b> zeigt die Ausführung des Anwendungsbeispiels mit OGS.</i></font></figcaption>
</figure><p>

</p>
</details>

Hinweis: Die Rechenzeit kann mehrere Stunden betragen.
Dies können Sie reduzierten, indem Sie in der Datei ***OGS3D_SAZOI_BETTINA*** unter folgenden Pfad ***.\ProjectLib\ExampleSetups*** öffnen und die folgende Zeile ändern:

	<delta_t_ogs> 604800 </delta_t_ogs>							 [7]

Hier werden **604800** Sekunden angegeben, diese Zahl kann variiert werden.
Sie entspricht hier einer Woche, d.h. die OGS-Berechnungen werden im Baummodell nicht für den Ausgangszeitschritt, sondern nur für eine Woche durchgeführt.
Aus den Ergebnissen wird die Porenwasserverteilung unter stationären Annahmen extrapoliert.
Folglich muss dieser Parameter sehr vorsichtig verwendet werden, ist aber ein Mittel, um die Rechenzeit deutlich zu reduzieren (siehe <a href="/de/docs/erste_schritte/erste_anwendungen_von_pymanga/#Abbildung_13">Abbildung 13</a>).

<figure>
<a name="Abbildung_13"></a>
<img src="/pictures/getting_started/first_applications_of_pymanga/set_timestep_length.jpg">
<figcaption><font size = "1"><i><b>Abbildung 13:</b> Anpassung zur Verkürzung der Rechenzeit.</i></font></figcaption>
</figure><p>

