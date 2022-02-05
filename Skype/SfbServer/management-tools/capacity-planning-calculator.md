---
title: 'Skype for Business Server: Rechner zur Kapazitätsplanung'
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
ms.date: 2/1/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: 'Zusammenfassung: Verwenden des Kapazitätsrechnertools.'
---

# <a name="skype-for-business-server-capacity-planning-calculator"></a>Skype for Business Server: Rechner zur Kapazitätsplanung
 
**Zusammenfassung:** So verwenden Sie das Kapazitätsrechnertool.

> [!NOTE]
> Dieser Artikel verweist auf Skype for Business Server 2015-Downloads, gilt jedoch für:
> - Skype for Business Server 2019.
> - Skype for Business Server 2015.
  
Der [Skype for Business Server 2015-Kapazitätsrechner](https://www.microsoft.com/download/details.aspx?id=51196) und [der Skype for Business Server 2019-Kapazitätsrechner](https://www.microsoft.com/download/details.aspx?id=57509) erweitern das [Skype for Business-Planungstool](https://www.microsoft.com/download/details.aspx?id=50357) und Ihre Bereitstellungsdokumentation ([Plan for Your Skype for Business Server 2015-Bereitstellung](../plan-your-deployment/plan-your-deployment.md) bzw. [-Planung für Ihre Skype for Business Server 2019-Bereitstellung](../../SfBServer2019/plan/plan-your-deployment-2019.md)). Verwenden Sie den Rechner, nachdem Sie die Anleitung überprüft und mithilfe des Planungstools eine empfohlene Topologie erstellt haben.
  
Der Skype for Business Server Kapazitätsrechner hilft Ihnen bei der Ermittlung der Serveranforderungen basierend auf der Anzahl der Benutzer und den Kommunikationstools, die Ihre Organisation verwendet. Nachdem Sie Ihr Benutzerprofil und die Funktionen bestimmt haben, die Sie für Ihre Benutzer aktivieren möchten, bestimmen Sie mithilfe des Rechners die Anzahl der Server, des Arbeitsspeichers und der Bandbreite, die Sie benötigen. Diese Version des Rechners bietet keine Anleitungen für Datenträger-E/A-Anforderungen.
  
Sie können am meisten vom Rechner profitieren, wenn Sie genaue, detaillierte Informationen zu Ihrem spezifischen Benutzerprofil haben. Beispielsweise können der Prozentsatz der voIP-aktivierten Benutzer, die durchschnittlichen Anrufe pro Benutzer und Stunde, die Anrufdauer und der Prozentsatz der gleichzeitigen Benutzer in Konferenzen einen großen Unterschied bei den Serveranforderungen ausmachen. Die Genauigkeit der vom Rechner erstellten Empfehlungen hängt von der Genauigkeit der von Ihnen bereitgestellten Informationen ab.
  
Nachdem Sie das Planungstool und den Rechner für die Kapazitätsplanung verwendet haben, sollten Sie die vorgeschlagene und geplante Last simulieren, um sicherzustellen, dass Skype for Business Server angemessen bereitgestellt werden. Verwenden Sie zum Durchführen von Belastungstests unter einer simulierten Last das [Skype for Business Server Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367), das im [Skype for Business Server Stress and Performance Tool](./stress-and-performance-tool/stress-and-performance-tool.md) dokumentiert ist.
  
## <a name="using-the-capacity-calculator"></a>Verwenden des Kapazitätsrechners

Der Rechner ist eine Microsoft Excel Tabellenkalkulation. Ihre Eingabezellen sind orangefarben. Standardwerte werden in die Zellen eingegeben (für Skype for Business Server 2015 80.000 Benutzer in einem Pool mit zwölf Front-End-Servern, während für Skype for Business Server 2019 106.000 Benutzer in einem Pool mit 16 Front-End-Servern) angegeben werden. Sie sollten diese Werte jedoch entsprechend den Anforderungen Ihrer Organisation ändern.
  
Das Verwendungsmodell enthält die folgenden Abschnitte. Geben Sie zum Berechnen der Kapazitätsanforderungen Daten wie oben im Blatt beschrieben ein, und arbeiten Sie zeilenweise nach unten: 
  
 **Chat und Anwesenheit**
  
- Geben Sie unter **"Anzahl der Benutzer**" die Anzahl der Benutzer ein, die gleichzeitig angemeldet sind. Diese Anzahl beträgt in der Regel 80 % der Gesamtzahl der bereitgestellten Benutzer. In den meisten Situationen werden 100 % Ihrer gleichzeitigen Benutzer für Chat und Anwesenheit aktiviert. Der Standardwert ist 80.000 für Skype for Business Server 2015 und 106.000 Benutzer für Skype for Business Server 2019.
    
- **Die durchschnittliche Anzahl von Kontakten in der Kontaktliste** gibt die Anzahl der Kontakte an, die wir verwenden, um Ihre Systemanforderungen zu überprüfen. Diese Zahl ist festgelegt und sollte nicht geändert werden.
    
  **Enterprise-VoIP**
  
- Geben Sie unter **Benutzer, die für Enterprise-VoIP aktiviert sind**, den Prozentsatz der Für Enterprise-VoIP aktivierten Benutzer ein. Der Standardwert ist 60 %. 
    
- Geben Sie **in der durchschnittlichen Anzahl der Anrufe pro Benutzer und Stunde (Spitzen)** die Anzahl der Anrufe pro Stunde ein, an denen der durchschnittliche Benutzer in Zeiten der Spitzenlast teilnehmen wird. Der Standardwert ist 4. 
    
- Geben **Sie in Prozent der Anrufe, die die Medienumgehung verwenden**, den Prozentsatz der Anrufe ein, die von Ihren Benutzern getätigt wurden, die den Vermittlungsserver umgehen. Der Standardwert ist 65 %, kann aber niedriger sein, wenn Sie geografisch verteilt sind oder einen großen Prozentsatz der Benutzer haben, die von zu Hause aus arbeiten.
    
- Geben **Sie in Prozent der VoIP-Benutzer, die an UC-PSTN-Anrufen beteiligt** sind, den Prozentsatz der Anrufe Ihrer Organisation ein, bei denen es sich um UC-PSTN-Telefonanrufe handelt. Der Standardwert ist 60 %.
    
- **Der Prozentsatz der VoIP-Benutzer, die an UC-UC-Anrufen beteiligt** sind, zeigt den Prozentsatz der Benutzer an, die für Enterprise-VoIP aktiviert sind, die nur für UC-UC-Anrufe aktiviert werden. Diese Zahl wird basierend auf der Eingabe für **den Prozentsatz der Sprachbenutzer berechnet, die für UC-PSTN-Anrufe aktiviert** sind. 
    
  **Konferenzen**
  
- Geben **Sie in Prozent der Benutzer in gleichzeitigen Konferenzen** den Prozentsatz der Benutzer ein, die gleichzeitig an Konferenzen teilnehmen werden. Der Standardwert ist 5 %. 
    
- Geben **Sie in Prozent der Konferenzen, die nur Gruppennachrichten enthalten (keine Stimme),** den Prozentsatz der Konferenzen ein, die nur Chatnachrichten umfassen und keine Audiodaten enthalten. Der Standardwert ist 10 %
    
- Geben **Sie in Prozent der Benutzer, die Einwahlkonferenzen** verwenden, den Prozentsatz der Teilnehmer an Konferenzen ein, die Einwahlkonferenzen gleichzeitig verwenden werden. Der Standardwert ist 15 %.
    
- Geben **Sie in Prozent der Konferenzen, die VoIP verwenden**, den Prozentsatz der Konferenzen ein, die Audio enthalten sollen. 
    
  - Wenn 20 % Ihrer Sprachkonferenzen auch reguläre Videos enthalten, aktivieren Sie das Kontrollkästchen **"Video einschließen" (keine Mehrfachansicht** ).
    
  - Wenn 20 % Ihrer Konferenzen auch Video mit mehrfacher Ansicht enthalten, aktivieren Sie das Kontrollkästchen **"Multiansicht** einschließen".
    
  - Wenn 50 % Ihrer VoIP-Konferenzen auch die Anwendungsfreigabe umfassen, aktivieren Sie das Kontrollkästchen **"Anwendungsfreigabe einschließen** ".
    
  - Wenn 20 % Ihrer VoIP-Konferenzen Datenuploads enthalten, z. B. PowerPoint Präsentationen, aktivieren Sie das Kontrollkästchen **"Webkonferenzen einschließen**".
    
  **Mobilität**
  
- Geben **Sie in Prozent der Benutzer, die für Mobilität aktiviert** sind, den Prozentsatz Der Benutzer ein, die über mobile Geräte eine Verbindung mit Skype for Business Server herstellen können. Der Standardwert ist 40 %. 
    
Wenn Sie alle erforderlichen Informationen eingegeben haben, schätzt der Kapazitätsrechner Ihre Anforderungen. Die gelben Zellen zeigen berechnete Werte für CPU-, Arbeitsspeicher- und Bandbreitenanforderungen basierend auf Tests, die in Skype for Business Server Leistungslabors durchgeführt wurden. Die Zahlen werden als Richtlinie bereitgestellt, nicht jede einzelne Variante wird getestet und überprüft. Die folgenden Werte werden berechnet: 
  
- **Front-End-CPU**: Prozentsatz der CPU-Auslastung, wenn die gesamte Last von einem Front-End-Server mit denselben Spezifikationen wie der Server verarbeitet wurde, der beim Testen verwendet wurde (siehe Beschreibung am Ende dieses Artikels).
    
- **Netzwerk in MBit/s**: Bandbreitenanforderungen in Megabit pro Sekunde (MBit/s) für die entsprechende Workload.
    
- **Arbeitsspeicher in GB**: Erforderlicher Arbeitsspeicher in Gigabyte (GB) für die entsprechende Workload.
    
Die grünen Zellen zeigen Empfehlungen für das von Ihnen eingegebene Nutzungsmodell an. 
  
- **Front-End-Server insgesamt**: Die Anzahl der erforderlichen physischen Server basiert auf dedizierten Servern, die Skype for Business Server 2015 mit dualem Prozessor, Hex-Core, 2.260 Megazyklen oder Skype for Business Server 2019 mit Intel Xeon E5-2673 v3, dualem Prozessor und Hex-Core ausgeführt werden.
    
    Beachten Sie, dass das Aktivieren von Hyperthreading empfohlen wird und die Leistung für Server, die Audio/Video unterstützen, nachgewiesen wurde.
    
- **Edgeserver**: Die Anzahl der erforderlichen Edgeserver, basierend auf 30 % aller gleichzeitigen Benutzer, die über die Edgeserver kommunizieren. Dieser Prozentsatz kann im Rechner nicht geändert werden. 
    
- **Dienste zur Archivierung/Aufzeichnung von Kommunikationsdatensätzen/Quality of Experience Store**: Die Anzahl der Speicher, die für Archivierungs- oder Überwachungsfeatures erforderlich sind, wenn sie in Ihrer Organisation aktiviert sind.
    
- **Back-End-Datenbankserver erforderlich (Pools erforderlich):** Die Anzahl der Back-End-Datenbankserver, die zur Unterstützung der ausgewählten Workload erforderlich sind.
    
Darüber hinaus werden in der Zeile neben den Front-End-Gesamtservern weitere Informationen zur Last auf Ihren Servern und im Netzwerk für alle geplanten Workloads zusammen bereitgestellt.
  
- **Durchschnittliche CPU-Auslastung**: Die durchschnittliche CPU-Auslastung pro Front-End-Server.
    
- **Netzwerk in MBit/s**: Die erforderliche Bandbreitenzuweisung, um das von Ihnen eingegebene Nutzungsmodell zu unterstützen.
    
- **Arbeitsspeicher in GB**: Arbeitsspeicher in Gigabyte, erforderlich für jeden Front-End-Server.
    
### <a name="adjusting-for-your-processors"></a>Berechnen der Leistungskennzahlen für Ihre Prozessoren

Alle CPU-Auslastungszahlen in der Tabelle gehen davon aus, dass jeder Skype for Business Server 2015-Server über einen dualen Prozessor, Hex-Core mit 2,26 GHz, mindestens 32 GB Arbeitsspeicher und mindestens 8 Festplattenlaufwerke mit 10.000 U/min und mindestens 72 GB freiem Speicherplatz verfügt. Für jeden Skype for Business Server 2019-Server gehen alle CPU-Auslastungszahlen in der Tabelle davon aus, dass jeder Server über einen dualen Prozessor, Hex-Core mit Intel Xeon E5-2673 v3, mindestens 64 GB Arbeitsspeicher und 8 oder mehr Festplattenlaufwerke mit 10.000 U/min und mindestens 72 GB freiem Speicherplatz verfügt.
  
Wenn Ihre Server unterschiedliche Prozessoren haben, können Sie die Abbildungen an Ihre Hardware anpassen.
