---
title: Arbeiten mit dem Rechner zur Kapazitätsplanung für Lync Server 2013
TOCTitle: Arbeiten mit dem Rechner zur Kapazitätsplanung für Lync Server 2013
ms:assetid: e86c1f05-1393-408a-9549-6001572ec50d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn362852(v=OCS.15)
ms:contentKeyID: 56269349
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Arbeiten mit dem Rechner zur Kapazitätsplanung für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Der Rechner zur Kapazitätsplanung für Microsoft® Lync™ Server 2013 ist unter dem Link <http://www.microsoft.com/en-us/download/details.aspx?id=36828> zum Download verfügbar. Er ist so konzipiert, dass er Sie dabei unterstützt, die Serveranforderungen anhand der Anzahl von Benutzern und anhand der Kommunikationsmodalitäten zu ermitteln, die in Ihrer Organisation aktiviert sind. Sie geben das Profil Ihrer Organisation ein, und der Rechner stellt Empfehlungen bereit, entsprechend denen Sie die Topologie planen können.

Die von dem Rechner erstellten Empfehlungen sind nur für Planungszwecke vorgesehen. Es sind tatsächliche Lastsimulationen erforderlich, um sicherzustellen, dass Lync Server 2013 angemessen bereitgestellt wird. Zum Ausführen von Stresstests unter einer simulierten Last verwenden Sie das [Lync Server 2013 Stress and Performance Tool](http://go.microsoft.com/fwlink/?linkid=282724).

Nachdem Sie Ihr Benutzerprofil und die Modalitäten bestimmt haben, die Sie für die Benutzer aktivieren möchten, verwenden Sie den Rechner dazu, die benötigten Ressourcen (Anzahl von Servern, Arbeitsspeicher und Bandbreite) zu planen. Diese Version des Rechners stellt keine Anleitung bezüglich der Datenträger-E/A-Anforderungen bereit.

Dieser Rechner ergänzt das [Microsoft Lync Server 2013 Planning Tool](http://go.microsoft.com/fwlink/?linkid=282725) sowie die [Planung](lync-server-2013-planning.md). Verwenden Sie den Rechner, nachdem Sie das Handbuch gelesen und mit dem Planning Tool die jeweils empfohlene Topologie erstellt haben.

Den besten Nutzen erzielen Sie mit dem Rechner, wenn Sie genaue und ausführliche Informationen zu Ihrem speziellen Benutzerprofil haben. Beispielsweise können der Prozentsatz von VoIP-aktivierten Benutzern, der Durchschnitt der Anrufe pro Benutzer und Stunde, die Anrufdauer und der Prozentsatz von gleichzeitigen Benutzern in Konferenzen einen großen Unterschied hinsichtlich der Serveranforderungen ausmachen. Die Genauigkeit der Empfehlungen, die vom Rechner erstellt werden, hängt von der Genauigkeit der Informationen ab, die Sie bereitgestellt haben.

## Arbeiten mit dem Kapazitätsrechner

Der Rechner ist ein Microsoft Excel®-Arbeitsblatt. Orangefarbene Zellen sind für Eingaben von Ihnen vorgesehen. Es sind bereits Standardwerte eingegeben (80.000 Benutzer in einem Pool mit zwölf Front-End-Servern), aber diese Werte können Sie entsprechend den Anforderungen Ihrer Organisation ändern.

Das Nutzungsmodell enthält die folgenden Abschnitte. Damit Sie Ihre Kapazitätsanforderungen berechnen können, geben Sie Daten gemäß der Beschreibung ein:

**Chat und Anwesenheit (Instant Messaging/Presence, IM/P)**

  - Geben Sie unter Anzahl der Benutzer die Anzahl von Benutzers ein, die gleichzeitig angemeldet sein können. Diese Anzahl entspricht meist 80 % der Gesamtanzahl der bereitgestellten Benutzer. In den meisten Situationen werden 100 % der gleichzeitigen Benutzer für Chat und Anwesenheit aktiviert. Der Standardwert ist 80.000.

  - Durchschnittliche Anzahl von Kontakten in der Kontaktliste gibt die Anzahl von Kontakten an, die zur Überprüfung Ihrer Systemanforderungen verwendet wird. Diese Anzahl kann nicht geändert werden.

**Enterprise-VoIP (Enterprise Voice)**

  - Geben Sie in Benutzer, für die Enterprise-VoIP aktiviert ist den Prozentsatz Ihrer Benutzer an, für die Enterprise-VoIP aktiviert werden soll. Der Standardwert ist 60 %.

  - Geben Sie in Durchschnittliche Anzahl von Anrufen pro Benutzer pro Stunde (Spitze) die Anzahl von Anrufen pro Stunde ein, die Sie für den durchschnittlichen Benutzer als Teilnehmer zu Spitzenlastzeiten erwarten. Der Standardwert ist 4.

  - Geben Sie Prozentsatz der Anrufe, die Medienumgehung nutzen den Prozentsatz der Anrufe ein, die von Ihren Benutzern getätigt, aber nicht über den Vermittlungsserver abgewickelt werden. Der Standardwert ist 65 %.

  - Geben in Prozentsatz der VoIP-Benutzer, die an UC-PSTN-Anrufen beteiligt sind den Prozentsatz der Anrufe in Ihrer Organisation ein, die Anrufe über das UC-Telefonfestnetz (UC-PSTN) sind. Der Standardwert ist 60 %

  - In Prozentsatz der VoIP-Benutzer, die an UC-UC-Anrufen beteiligt sind ist der Prozentsatz der Benutzer enthalten, die zwar für Enterprise-VoIP, aber nur für UC-UC-Anrufe aktiviert sind. Diese Anzahl wird auf Basis des Werts berechnet, den Sie in Prozentsatz der VoIP-Benutzer, die an UC-PSTN-Anrufen beteiligt sind eingegeben haben.

**Konferenzfunktion (Conferencing)**

  - Geben Sie in Prozentsatz der Benutzer in gleichzeitigen Konferenzen den Prozentsatz von Benutzern ein, die gleichzeitig an einer Konferenz teilnehmen. Der Standardwert ist 5 %.

  - Geben Sie in Prozentsatz der Konferenzen nur mit Gruppenchat (kein VoIP) den Prozentsatz von Konferenzen ein, für die ausschließlich Chat genutzt wird, d. h., sie beinhalten keine Audiokomponenten. Der Standardwert ist 10 %

  - Geben Sie in Prozentsatz der Benutzer, die Einwahlkonferenzen verwenden den Prozentsatz von gleichzeitigen Teilnehmern ein, die Einwahlkonferenzen verwenden. Der Standardwert ist 15 %.

  - Geben Sie in Prozentsatz der Konferenzen mit VoIP den Prozentsatz von Konferenzen ein, die Audiokomponenten beinhalten.
    
      - Wenn 20 % Ihrer VoIP-Konferenzen auch normale Videoelemente beinhalten, aktivieren Sie das Kontrollkästchen Einschließlich Video (kein Multiview).
    
      - Wenn 20 % Ihrer Konferenzen auch Multiview-Videoelemente beinhalten, aktivieren Sie das Kontrollkästchen Einschließlich Multiview.
    
      - Wenn 50 % Ihrer VoIP-Konferenzen auch Anwendungsfreigabe beinhalten, aktivieren Sie das Kontrollkästchen Einschließlich Anwendungsfreigabe.
    
      - Wenn 20 % Ihrer VoIP-Konferenzen Datenuploads beinhalten, etwa Microsoft PowerPoint®-Präsentationen, aktivieren Sie das Kontrollkästchen Einschließlich Webkonferenzen.

**Mobilität (Mobility)**

  - Geben Sie in Prozentsatz der Benutzer, für die Mobilität aktiviert ist den Prozentsatz von Benutzern ein, denen es möglich sein soll, über mobile Geräte Verbindungen mit Lync Server herzustellen. Der Standardwert ist 40 %.

Wenn Sie alle erforderlichen Informationen eingegeben haben, berechnet der Kapazitätsrechner Ihre Anforderungen. In den gelben Zellen werden die berechneten Werte für CPU-, Arbeitsspeicher- und Bandbreitenanforderungen angezeigt. Diese basieren auf Tests, die in Lync Server 2013-Leistungsuntersuchungen ausgeführt wurden. Die Werte werden als Richtlinien bereitgestellt, es wird nicht jede einzelne Variation getestet und überprüft. Die folgenden Werte werden berechnet:

  - Front-End-CPU: Prozentsatz der CPU-Nutzung, wenn die gesamte Last von einem Front-End-Server verarbeitet wurde, der dieselben Spezifikationen hat wie der Server, der für die Microsoft-Tests verwendet wurde.

  - Netzwerk in Mbit/s: Bandbreitenanforderungen in Megabit pro Sekunde (MBit/s) für die entsprechende Arbeitsauslastung.

  - Arbeitsspeicher in MB: Arbeitsspeicher in Gigabyte (GB), der für die entsprechende Arbeitsauslastung erforderlich ist.

In den grünen Zellen werden Empfehlungen für das Nutzungsmodell angezeigt, das Sie eingegeben haben.

  - Gesamtanzahl der Front-End-Server erforderliche: Die Anzahl von erforderlichen physischen Servern basiert auf speziell dafür vorgesehenen Servern, auf denen Lync Server 2013 ausgeführt wird und die jeweils einen Dualprozessor mit sechs Kernen und 2.260 Megahertz haben.

  - Es wird empfohlen, Hyperthreading zu aktivieren, denn damit lässt sich nachweislich die Leistung von Servern verbessern, die Audio/Video unterstützen.

  - Edgeserver: Die Anzahl von erforderlichen Edgeservern. Diese Anzahl basiert auf 30 % aller gleichzeitigen Benutzer, die über die Edgeserver kommunizieren. Dieser Prozentsatz kann im Rechner nicht geändert werden.

  - Speicher für die Dienste Archivierung/Aufzeichnung von Kommunikationsdatensätzen/Quality of Experience: Die Anzahl von Speichern, die für Archivierungs- oder Überwachungsfeatures erforderlich sind, sofern diese in Ihrer Organisation aktiviert sind.

  - Erforderliche Back-End-Datenbankserver (erforderliche Pools): Die Anzahl von Back-End-Datenbankservern, die erforderlich sind, damit die ausgewählte Auslastung unterstützt werden kann.

Die Zeile neben Gesamtanzahl der Front-End-Server enthält zusätzlich weitere Informationen zu der Last auf den Servern und im Netzwerk für alle geplanten Auslastungen in Kombination.

  - Durchschnittliche CPU-Auslastung: Die durchschnittliche CPU-Nutzung pro Front-End-Server.

  - Netzwerk in Mbit/s: Die Bandbreitenzuteilung, die erforderlich ist, damit das von Ihnen eingegebene Nutzungsmodell unterstützt wird.

  - Arbeitsspeicher in MB: Der Arbeitsspeicher in Gigabyte, der für jeden Front-End-Server erforderlich ist.

## Anpassen an Ihre Prozessoren

Für alle CPU-Nutzungswerte auf dem Arbeitsblatt wird angenommen, dass jeder Server einen Dualprozessor mit sechs Kernen und 2,26 GHz, mindestens 32 GB Arbeitsspeicher und mindestens 8 10.000-U/min-Festplattenlaufwerke mit mindestens 72 GB freiem Speicherplatz hat.

Wenn Ihre Server andere Prozessoren haben, können Sie die Werte entsprechend Ihrer Hardware anpassen.

