---
title: Skype for Business Server Kapazitäts planungsrechner
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Zusammenfassung: Verwenden des Kapazitäts Rechner Tools'
ms.openlocfilehash: 1bb1c9cde82c1f2d6e487c3bc28520b630d59210
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031079"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a>Skype for Business Server Kapazitäts planungsrechner
 
**Zusammenfassung:** Verwenden des Kapazitäts Rechner Tools

> [!NOTE]
> Dieser Artikel verweist auf Skype for Business Server 2015 Downloads, gilt jedoch für:
> - Skype for Business Server 2019.
> - Skype for Business Server 2015.
  
Der [Skype for Business Server 2015 Kapazitäts Rechner](https://www.microsoft.com/download/details.aspx?id=51196) und [Skype for Business Server Kapazitäts Rechner mit 2019](https://www.microsoft.com/download/details.aspx?id=57509) erweitern das [Skype for Business-Planungs Tool](https://www.microsoft.com/download/details.aspx?id=50357) und die Bereitstellungsdokumentation ([Planen der Skype for Business Server 2015 Bereitstellung](../plan-your-deployment/plan-your-deployment.md) und [Planen der Skype for Business Server 2019-bereit](../../SfBServer2019/plan/plan-your-deployment-2019.md) Stellung jeweils). Verwenden Sie den Rechner, nachdem Sie das Handbuch überprüft und eine empfohlene Topologie mithilfe des Planungstools erstellt haben.
  
Der Skype for Business Server Kapazitäts Rechner hilft Ihnen bei der Ermittlung der Server Anforderungen basierend auf der Anzahl der Benutzer und der Kommunikationstools, die Ihre Organisation verwendet. Nachdem Sie Ihr Benutzerprofil und die Funktionen bestimmt haben, die Sie für Ihre Benutzer aktivieren möchten, verwenden Sie den Rechner, um die Anzahl der Server, des Arbeitsspeichers und der Bandbreite zu ermitteln, die Sie benötigen. Diese Version des Rechners bietet keine Anleitung für Datenträger-e/a-Anforderungen.
  
Sie können am meisten von dem Rechner profitieren, wenn Sie genaue, detaillierte Informationen zu Ihrem bestimmten Benutzerprofil haben. Beispielsweise kann der Prozentsatz an sprachaktivierten Benutzern, durchschnittliche Anrufe pro Benutzer und Stunde, Anrufdauer und der Prozentsatz gleichzeitiger Benutzer in Konferenzen einen großen Unterschied in den Server Anforderungen mit sich bringen. Die Genauigkeit der vom Rechner erstellten Empfehlungen hängt von der Genauigkeit der von Ihnen bereitgestellten Informationen ab.
  
Nachdem Sie das Planungs Tool und den Kapazitäts planungsrechner verwendet haben, sollten Sie die vorgeschlagene und geplante Last simulieren, um sicherzustellen, dass Skype for Business Server angemessen bereitgestellt werden. Verwenden Sie zum Ausführen von Belastungstests unter simulierter Last das Tool [Skype for Business Server Stress and Performance](https://www.microsoft.com/download/details.aspx?id=50367) , das unter [Skype for Business Server Stress and Performance Tool](https://technet.microsoft.com/library/mt631400.aspx)dokumentiert ist.
  
## <a name="using-the-capacity-calculator"></a>Verwenden des Kapazitäts Rechners

Der Rechner ist eine Microsoft Excel Tabelle. Die Eingabezellen sind orange gefärbt. Standardwerte werden in die Zellen eingegeben (für Skype for Business Server 2015 80.000 Benutzer in einem Pool mit zwölf Front-End-Servern, während für Skype for Business Server 2019, 106.000 Benutzer in einem Pool mit sechzehn Front-End-Servern), aber Sie sollten diese Werte ändern, um entsprechen den Anforderungen Ihrer Organisation.
  
Das Nutzungsmodell enthält die folgenden Abschnitte. Geben Sie zum Berechnen der Kapazitätsanforderungen Daten wie beschrieben ein, beginnend am oberen Rand des Arbeitsblatts und Zeile für Zeile: 
  
 **Instant Messaging und Anwesenheit**
  
- Geben Sie unter **Anzahl der Benutzer**die Anzahl der Benutzer ein, die gleichzeitig angemeldet werden sollen. Diese Nummer ist normalerweise 80% der Gesamtzahl der gestellten Benutzer. In den meisten Fällen sind 100% ihrer gleichzeitigen Benutzer für Sofortnachrichten und Anwesenheitsinformationen aktiviert. Der Standardwert ist 80.000 für Skype for Business Server 2015-und 106.000-Benutzer für Skype for Business Server 2019.
    
- **Durchschnittliche Anzahl von Kontakten in der Kontaktliste** gibt die Anzahl der Kontakte an, die für die Überprüfung der Systemanforderungen verwendet werden. Diese Nummer ist fix und nicht etwas, das Sie ändern sollten.
    
  **Enterprise-VoIP**
  
- Geben Sie unter **für Enterprise-VoIP aktivierte Benutzer**den Prozentsatz der für Enterprise-VoIP aktivierten Benutzer ein. Der Standardwert ist 60%. 
    
- Geben Sie im **Durchschnitt Anzahl der Anrufe pro Benutzer und Stunde (Spitzenwert)** die Anzahl der Anrufe pro Stunde ein, die der durchschnittliche Benutzer in Zeiten der Spitzenauslastung an der Teilnahme erwartet. Der Standardwert ist 4. 
    
- Geben Sie in **Prozentsatz der Anrufe, die die medienumgehung verwenden**, den Prozentsatz der Anrufe ein, die von Ihren Benutzern getätigt werden und die Vermittlungsserver umgehen. Der Standardwert ist 65%, kann jedoch niedriger sein, wenn Sie geografisch verteilt sind oder einen großen Prozentsatz von Benutzern haben, die von zu Hause aus arbeiten.
    
- Geben Sie in **Prozentsatz der VoIP-Benutzer, die an UC-PSTN-anrufen beteiligt**sind, den Prozentsatz der Anrufe Ihrer Organisation ein, bei denen es sich um UC-PSTN-Telefonanrufe handelt. Der Standardwert ist 60%.
    
- **Prozentsatz der an UC-UC-Anrufe beteiligten Sprachbenutzer** zeigt den Prozentsatz der Benutzer an, die für Enterprise-VoIP aktiviert sind und nur für UC-UC-Anrufe aktiviert werden. Diese Nummer wird basierend auf den Angaben berechnet, die Sie für den **Prozentsatz der für UC-PSTN-Anrufe aktivierten VoIP-Benutzer**eingegeben haben. 
    
  **Konferenzen**
  
- Geben Sie in **Prozentsatz der Benutzer in gleich**zeitigen Konferenzen den Prozentsatz der Benutzer ein, die gleichzeitig an Konferenzen teilnehmen werden. Der Standardwert ist 5%. 
    
- Geben Sie in **Prozentsatz der Konferenzen mit nur Gruppen-Chat (keine Stimme)** den Prozentsatz der Konferenzen ein, bei denen nur Chatnachrichten berücksichtigt werden sollen, und fügen Sie keine Audiodaten hinzu. Der Standardwert ist 10%
    
- Geben Sie in **Prozentsatz der Benutzer, die Einwahlkonferenzen verwenden**, den Prozentsatz der Teilnehmer an Konferenzen ein, die Einwahlkonferenzen gleichzeitig verwenden werden. Der Standardwert ist 15%.
    
- Geben Sie in **Prozentsatz der Konferenzen, die VoIP verwenden**, den Prozentsatz der Konferenzen ein, die Audiodaten enthalten sollen. 
    
  - Wenn 20% Ihrer VoIP-Konferenzen auch reguläre Videos enthalten, aktivieren Sie das Kontrollkästchen **einschließlich Video (keine Mehrfachansicht)** .
    
  - Wenn 20% ihrer Konferenzen auch Multi-View-Video enthalten, aktivieren Sie das Kontrollkästchen **einschließlich Multiview-Ansicht** .
    
  - Wenn 50% Ihrer VoIP-Konferenzen auch die Anwendungsfreigabe umfassen, aktivieren Sie das Kontrollkästchen **einschließlich Anwendungsfreigabe** .
    
  - Wenn 20% Ihrer VoIP-Konferenzen Datenuploads wie PowerPoint-Präsentationen umfassen, aktivieren Sie das Kontrollkästchen **einschließlich Webkonferenzen** .
    
  **Mobilität**
  
- Geben Sie in **Prozentsatz der für Mobilität aktivierten Benutzer**den Prozentsatz der Benutzer ein, die zum Herstellen einer Verbindung mit Skype for Business Server über mobile Geräte aktiviert werden sollen. Der Standardwert ist 40%. 
    
Wenn Sie alle erforderlichen Informationen eingegeben haben, schätzt der Kapazitäts Rechner Ihre Anforderungen. Die gelben Zellen zeigen berechnete Werte für CPU-, Arbeitsspeicher-und Bandbreitenanforderungen basierend auf Tests an, die in Skype for Business Server Performance Labs ausgeführt werden. Die Zahlen werden als Richtlinie bereitgestellt, nicht jede einzelne Variation wird getestet und validiert. Die folgenden Werte werden berechnet: 
  
- **Front-End-CPU**: Prozentsatz der CPU-Auslastung, wenn die gesamte Last von einem Front-End-Server der gleichen Spezifikationen wie der Server, der zum Testen verwendet wurde, verarbeitet wurde (siehe die Beschreibung am Ende dieses Artikels).
    
- **Netzwerk in Mbit/s**: Bandbreitenanforderungen in Megabit pro Sekunde (Mbit/s) für die entsprechende Arbeitsauslastung.
    
- **Arbeitsspeicher in GB**: erforderlicher Arbeitsspeicher in Gigabyte (GB) für die entsprechende Arbeitsauslastung.
    
Die grünen Zellen zeigen Empfehlungen für das von Ihnen eingegebene Nutzungsmodell an. 
  
- **Gesamtzahl der Front-End-Server**: die erforderliche Anzahl physischer Server basiert auf dedizierten Servern, auf denen Skype for Business Server 2015 mit Dualprozessor, Hex-Kern, 2.260 Megazyklen oder Skype for Business Server 2019 mit Intel Xeon E5-2673 v3, Dualprozessor, Hex-Core, basieren.
    
    Beachten Sie, dass die Aktivierung von Hyperthreading empfohlen wird und dass die Leistung für Server verbessert wurde, die Audio/Video unterstützen.
    
- **Edgeserver**: die Anzahl der erforderlichen Edgeserver, basierend auf 30% aller gleichzeitigen Benutzer, die über die Edgeserver kommunizieren. Dieser Prozentsatz kann im Rechner nicht geändert werden. 
    
- **Archivierung/Anruf Detail Aufzeichnung/Quality of Experience Services Store**: die Anzahl der Speicher, die für Archivierungs-oder Überwachungsfeatures erforderlich sind, sofern diese in Ihrer Organisation aktiviert sind.
    
- **Back-End-Datenbankserver erforderlich (erforderliche Pools)**: die Anzahl der Back-End-Datenbankserver, die zur Unterstützung der ausgewählten Arbeitsauslastung erforderlich sind.
    
Darüber hinaus werden in der Zeile neben Gesamt-Front-End-Server Weitere Informationen zur Last auf den Servern und im Netzwerk für alle geplanten Arbeitslasten bereitgestellt.
  
- **Durchschnittliche CPU-Auslastung**: die durchschnittliche CPU-Auslastung pro Front-End-Server.
    
- **Netzwerk in Mbit/s**: die erforderliche Bandbreitenzuweisung zur Unterstützung des von Ihnen eingegebenen Nutzungs Modells.
    
- **Arbeitsspeicher in GB**: Arbeitsspeicher in Gigabyte, erforderlich für jeden Front-End-Server.
    
### <a name="adjusting-for-your-processors"></a>Berechnen der Leistungskennzahlen für Ihre Prozessoren

Bei allen CPU-Auslastungszahlen in der Tabelle wird davon ausgegangen, dass jeder Skype for Business Server 2015 Server über einen Dualprozessor, einen Hex-Kern mit 2,26 GHz, mindestens 32 GB Arbeitsspeicher und 8 oder mehr Festplatten mit 10.000-RPM mit mindestens 72 GB freiem Speicherplatz verfügt. Für jeden Skype for Business Server 2019-Server wird davon ausgegangen, dass auf jedem Server ein Dualprozessor, ein Hex-Core mit Intel Xeon E5-2673 v3, mindestens 64 GB Arbeitsspeicher und 8 oder mehr 10.000-rpm-Festplattenlaufwerke mit mindestens 72 GB freiem Datenträger vorhanden sind. Tempo.
  
Wenn Ihre Server unterschiedliche Prozessoren haben, können Sie die Zahlen so anpassen, dass Sie mit Ihrer Hardware übereinstimmen.
  
