---
title: 'Skype for Business Server: Rechner zur Kapazitätsplanung'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 2/1/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: 'Zusammenfassung: Verwenden des Kapazitätsrechnertools.'
ms.openlocfilehash: cc78e9d5cbf22a9cc194f0a434f246a8560f5382
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098881"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a>Skype for Business Server: Rechner zur Kapazitätsplanung
 
**Zusammenfassung:** Verwenden des Kapazitätsrechnertools.

> [!NOTE]
> Dieser Artikel verweist auf Skype for Business Server 2015-Downloads, gilt jedoch für:
> - Skype for Business Server 2019.
> - Skype for Business Server 2015.
  
Der [Skype for Business Server 2015-Kapazitätsrechner](https://www.microsoft.com/download/details.aspx?id=51196) und der Skype for Business Server [2019-Kapazitätsrechner](https://www.microsoft.com/download/details.aspx?id=57509) erweitern das [Skype for Business Planning Tool](https://www.microsoft.com/download/details.aspx?id=50357) und Ihre Bereitstellungsdokumentation ( Planen Ihrer Skype for Business Server[2015-Bereitstellung](../plan-your-deployment/plan-your-deployment.md) und Planen Ihrer [Skype for Business Server 2019-Bereitstellung).](../../SfBServer2019/plan/plan-your-deployment-2019.md) Verwenden Sie den Rechner, nachdem Sie das Handbuch überprüft und mithilfe des Planungstools eine empfohlene Topologie erstellt haben.
  
Der Kapazitätsrechner für Skype for Business Server hilft Ihnen bei der Ermittlung der Serveranforderungen basierend auf der Anzahl der Benutzer und den von Ihrer Organisation verwendeten Kommunikationstools. Nachdem Sie Ihr Benutzerprofil und die Funktionen bestimmt haben, die Sie für Ihre Benutzer aktivieren möchten, verwenden Sie den Rechner, um die Anzahl der Benötigten Server, Arbeitsspeicher und Bandbreite zu ermitteln. Diese Version des Rechners bietet keine Anleitungen für E/A-Anforderungen für Datenträger.
  
Sie können am meisten vom Rechner profitieren, wenn Sie über genaue, detaillierte Informationen zu Ihrem bestimmten Benutzerprofil verfügen. Beispielsweise können der Prozentsatz der sprachfähigen Benutzer, die durchschnittlichen Anrufe pro Benutzer pro Stunde, die Anrufdauer und der Prozentsatz gleichzeitiger Benutzer in Konferenzen einen großen Unterschied bei den Serveranforderungen machen. Die Genauigkeit der vom Rechner erstellten Empfehlungen hängt von der Genauigkeit der von Ihnen zur Verfügung stellten Informationen ab.
  
Nachdem Sie das Planungstool und den Kapazitätsplanungsrechner verwendet haben, sollten Sie die vorgeschlagene und geplante Auslastung simulieren, um sicherzustellen, dass Skype for Business Server angemessen bereitgestellt wird. Verwenden Sie das Skype for Business [Server Stress and Performance Tool,](https://www.microsoft.com/download/details.aspx?id=50367) das unter Skype for Business Server Stress and Performance Tool dokumentiert ist, um Stresstests unter simulierter Last [durchzuführen.](./stress-and-performance-tool/stress-and-performance-tool.md)
  
## <a name="using-the-capacity-calculator"></a>Verwenden des Kapazitätsrechners

Der Rechner ist eine Microsoft Excel-Kalkulationstabelle. Ihre Eingabezellen sind orange gefärbt. Standardwerte werden in die Zellen eingegeben (Für Skype for Business Server 2015 sind 80.000 Benutzer in einem Pool mit zwölf Front-End-Servern vorhanden, während für Skype for Business Server 2019 106.000 Benutzer in einem Pool mit sechzehn Front-End-Servern vorhanden sind), Sie sollten diese Werte jedoch an die Anforderungen Ihrer Organisation anpassen.
  
Das Verwendungsmodell enthält die folgenden Abschnitte. Um Ihre Kapazitätsanforderungen zu berechnen, geben Sie Daten wie oben im Blatt beschrieben ein, und arbeiten Sie Zeile für Zeile nach unten: 
  
 **Instant Messaging und Anwesenheit**
  
- Geben **Sie unter Anzahl der Benutzer** die Anzahl der Benutzer ein, die gleichzeitig angemeldet werden sollen. Diese Anzahl beträgt in der Regel 80 % der Gesamtzahl der bereitgestellten Benutzer. In den meisten Fällen werden 100 % der gleichzeitigen Benutzer für Denk- und Anwesenheitsfall aktiviert. Die Standardeinstellung ist 80.000 für Skype for Business Server 2015 und 106.000 Benutzer für Skype for Business Server 2019.
    
- **Die durchschnittliche Anzahl von** Kontakten in der Kontaktliste gibt die Anzahl der Kontakte an, die wir zum Überprüfen Ihrer Systemanforderungen verwenden. Diese Zahl ist behoben und sollte nicht geändert werden.
    
  **Enterprise-VoIP**
  
- Geben **Sie unter** Enterprise-VoIP aktivierte Benutzer den Prozentsatz der Benutzer ein, die für die Enterprise-VoIP. Der Standardwert ist 60 %. 
    
- Geben Sie unter Durchschnittliche Anzahl von Anrufen pro Benutzer pro Stunde **(Spitzenwert)** die Anzahl der Anrufe pro Stunde ein, an der der durchschnittliche Benutzer in Spitzenzeiten teilnehmen soll. Der Standardwert ist 4. 
    
- Geben **Sie unter Prozentsatz der Anrufe, die die Medienumgehung** verwenden, den Prozentsatz der Anrufe ein, die von Ihren Benutzern, die den Vermittlungsserver umgehen, ausgeführt werden. Der Standardwert ist 65 %, kann jedoch niedriger sein, wenn Sie geografisch verteilt sind oder einen großen Prozentsatz von Benutzern haben, die von zu Hause aus arbeiten.
    
- Geben Sie unter Prozentsatz der Sprachbenutzer, die **an UC-PSTN-Anrufen** beteiligt sind, den Prozentsatz der Anrufe Ihrer Organisation ein, bei denen es sich um UC-PSTN-Telefonanrufe handelt. Der Standardwert ist 60 %.
    
- **Der Prozentsatz der Sprachbenutzer, die an UC-UC-Anrufen** beteiligt sind, gibt den Prozentsatz der Benutzer an, die für Enterprise-VoIP aktiviert sind, die nur für UC-UC-Anrufe aktiviert werden. Diese Zahl wird basierend auf der Eingabe für Prozentsatz der für **UC-PSTN-Anrufe** aktivierten Sprachbenutzer berechnet. 
    
  **Konferenzen**
  
- Geben **Sie unter Prozentsatz der Benutzer in gleichzeitigen** Konferenzen den Prozentsatz der Benutzer ein, die gleichzeitig an Konferenzen teilnehmen. Der Standardwert ist 5 %. 
    
- Geben Sie unter Prozentsatz der Konferenzen mit nur Gruppennachrichten **(keine Sprachausgabe)** den Prozentsatz der Konferenzen ein, die nur Instant Messaging enthalten und keine Audiodaten enthalten. Der Standardwert ist 10 %
    
- Geben **Sie unter** Prozentsatz der Benutzer, die Einwahlkonferenzen verwenden, den Prozentsatz der Teilnehmer an Konferenzen ein, die Einwahlkonferenzen gleichzeitig verwenden. Der Standardwert ist 15 %.
    
- Geben **Sie unter Prozentsatz der Konferenzen mit Sprachausgabe** den Prozentsatz der Konferenzen ein, die Audio enthalten. 
    
  - Wenn 20 % Ihrer Sprachkonferenzen auch reguläre Videos enthalten, aktivieren Sie das Kontrollkästchen Video **(keine Mehransicht)** enthalten.
    
  - Wenn 20 % Ihrer Konferenzen auch Video mit mehreren Ansichtsansichten enthalten, aktivieren Sie das Kontrollkästchen **Multiansicht** enthalten.
    
  - Wenn 50 % Ihrer Sprachkonferenzen auch die Anwendungsfreigabe umfassen, aktivieren Sie das Kontrollkästchen **Anwendungsfreigabe** enthalten.
    
  - Wenn 20 % Ihrer Sprachkonferenzen Datenuploads enthalten, z. B. PowerPoint-Präsentationen, aktivieren Sie das Kontrollkästchen **Webkonferenzen** enthalten.
    
  **Mobilität**
  
- Geben **Sie unter** Prozentsatz der für Mobilität aktivierten Benutzer den Prozentsatz Ihrer Benutzer ein, die über mobile Geräte eine Verbindung mit Skype for Business Server herstellen können. Der Standardwert ist 40 %. 
    
Wenn Sie alle erforderlichen Informationen eingegeben haben, schätzt der Kapazitätsrechner Ihre Anforderungen. Die gelben Zellen zeigen berechnete Werte für CPU-, Arbeitsspeicher- und Bandbreitenanforderungen basierend auf Tests in Skype for Business Server-Leistungslabors. Die Zahlen werden als Richtlinie bereitgestellt, nicht jede einzelne Variante wird getestet und überprüft. Die folgenden Werte werden berechnet: 
  
- **Front-End-CPU:** Prozentsatz der CPU-Auslastung, wenn die gesamte Last von einem Front-End-Server mit denselben Spezifikationen wie der Server verarbeitet wurde, der bei Tests verwendet wurde (siehe beschreibung am Ende dieses Artikels).
    
- **Netzwerk in MBit/s:** Bandbreitenanforderungen in Megabits pro Sekunde (MBit/s) für die entsprechende Arbeitsauslastung.
    
- **Arbeitsspeicher in GB**: Arbeitsspeicher erforderlich in Gigabyte (GB) für die entsprechende Arbeitsauslastung.
    
In den grünen Zellen werden Empfehlungen für das von Ihnen eingegebene Verwendungsmodell gezeigt. 
  
- **Front-End-Server** insgesamt: Die Anzahl der erforderlichen physischen Server basiert auf dedizierten Servern, auf denen Skype for Business Server 2015 mit Dualprozessor, Hex-Core mit 2.260 Megazyklen oder Skype for Business Server 2019 mit Intel Xeon E5-2673 v3, Dualprozessor, Hex-Core ausgeführt wird.
    
    Beachten Sie, dass die Aktivierung von Hyperthreading empfohlen wird und sich als Leistungssteigerung für Server erwiesen hat, die Audio/Video unterstützen.
    
- **Edgeserver**: Die Anzahl der erforderlichen Edgeserver, basierend auf 30 % aller gleichzeitigen Benutzer, die über die Edgeserver kommunizieren. Dieser Prozentsatz kann im Rechner nicht geändert werden. 
    
- **Archivierungs-/Anrufdetailaufzeichnung/Quality of Experience Services Store**: Die Anzahl der Speicher, die für Archivierungs- oder Überwachungsfeatures erforderlich sind, sofern diese in Ihrer Organisation aktiviert sind.
    
- **Back-End-Datenbankserver erforderlich (Pools erforderlich):** Die Anzahl der Back-End-Datenbankserver, die zur Unterstützung der ausgewählten Arbeitsauslastung erforderlich sind.
    
Darüber hinaus finden Sie in der Zeile neben Den Front-End-Servern insgesamt weitere Informationen zur Last auf Ihren Servern und im Netzwerk für alle geplanten Arbeitsauslastungen zusammen.
  
- **Durchschnittliche CPU-Auslastung:** Die durchschnittliche CPU-Auslastung pro Front-End-Server.
    
- **Netzwerk in MBit/s:** Die erforderliche Bandbreitenzuweisung zur Unterstützung des von Ihnen eingegebenen Verwendungsmodells.
    
- **Arbeitsspeicher in GB:** Arbeitsspeicher in Gigabyte, erforderlich für jeden Front-End-Server.
    
### <a name="adjusting-for-your-processors"></a>Berechnen der Leistungskennzahlen für Ihre Prozessoren

Bei allen Zahlen zur CPU-Auslastung in der Tabelle wird davon ausgegangen, dass jeder Skype for Business Server 2015-Server über einen Dualprozessor, einen Hex-Core mit 2,26 GHz, mindestens 32 GB Arbeitsspeicher und mindestens 8 Festplattenlaufwerke mit mindestens 10.000 U/min mit mindestens 72 GB freiem Speicherplatz verfügt. Für jeden Skype for Business Server 2019-Server gehen alle Zahlen zur CPU-Auslastung in der Tabelle davon aus, dass jeder Server über einen Dualprozessor, einen Hex-Core mit Intel Xeon E5-2673 v3, mindestens 64 GB Arbeitsspeicher und mindestens 8 Festplattenlaufwerke mit mindestens 10.000 U/Min. mit mindestens 72 GB freiem Festplattenspeicher verfügt.
  
Wenn Ihre Server über unterschiedliche Prozessoren verfügen, können Sie die Zahlen an Ihre Hardware anpassen.
