---
title: 'Skype for Business Server: Rechner zur Kapazitätsplanung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/1/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: 'Zusammenfassung: Wie Sie das Kapazitätsrechnertool verwenden.'
ms.openlocfilehash: 24e268c6ecc3cc48fbfb4405f1e5e6b008639944
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274457"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a>Skype for Business Server: Rechner zur Kapazitätsplanung
 
**Zusammenfassung:** Wie Sie das Kapazitätsrechnertool verwenden.

> [!NOTE]
> Dieser Artikel bezieht sich auf Skype for Business Server 2015-Downloads, gilt aber für:
> - Skype for Business Server 2019.
> - Skype for Business Server 2015.
  
Der [Skype for Business Server 2015-Kapazitäts Rechner](https://www.microsoft.com/en-us/download/details.aspx?id=51196) und der [Skype for Business Server 2019-Kapazitäts Rechner](https://www.microsoft.com/en-us/download/details.aspx?id=57509) ergänzen das [Skype for Business-Planungs Tool](https://www.microsoft.com/en-us/download/details.aspx?id=50357) und ihre Bereitstellungsdokumentation ([Plan für Ihr Skype for Business Server 2015](../plan-your-deployment/plan-your-deployment.md) -Bereitstellung und [Plan für Ihre Skype for Business Server 2019-Bereitstellung](../../SfBServer2019/plan/plan-your-deployment-2019.md) . Verwenden Sie den Rechner, nachdem Sie die Anleitung gelesen und mithilfe des Planungstools eine empfohlene Topologie erstellt haben.
  
Mit dem Skype for Business Server-Kapazitäts Rechner können Sie die Server Anforderungen anhand der Anzahl der Benutzer und der Kommunikationstools ermitteln, die in Ihrer Organisation verwendet werden. Nachdem Sie Ihr Benutzerprofil und die Funktionen festgelegt haben, die Sie Ihren Nutzern zur Verfügung stellen möchten, verwenden Sie den Rechner zur Bestimmung der Anzahl von Servern, des Speicherumfangs und der Bandbreite, die erforderlich sein wird. Diese Version des Rechners bietet keine Anleitungen in Hinblick auf Datenträger-E/A-Anforderungen.
  
Den besten Nutzen erzielen Sie mit dem Rechner, wenn Sie genaue und ausführliche Informationen zu Ihrem speziellen Benutzerprofil haben. Beispielsweise können der Prozentsatz von VoIP-aktivierten Benutzern, der Durchschnitt der Anrufe pro Benutzer und Stunde, die Anrufdauer und der Prozentsatz von gleichzeitigen Benutzern in Konferenzen einen großen Unterschied hinsichtlich der Serveranforderungen ausmachen. Die Genauigkeit der Empfehlungen, die vom Rechner erstellt werden, hängt von der Genauigkeit der Informationen ab, die Sie bereitgestellt haben.
  
Nachdem Sie das Planungs Tool und den Kapazitäts planungsrechner verwendet haben, sollten Sie die vorgeschlagene und geplante Auslastung simulieren, um sicherzustellen, dass Skype for Business Server angemessen bereitgestellt wird. Wenn Sie Stresstests unter einer simulierten Belastung durchführen möchten, verwenden Sie das [Skype for Business Server Stress and Performance Tool](https://www.microsoft.com/en-us/download/details.aspx?id=50367) , das auf dem [Skype for Business Server Stress and Performance Tool](https://technet.microsoft.com/en-us/library/mt631400.aspx)dokumentiert ist.
  
## <a name="using-the-capacity-calculator"></a>Arbeiten mit dem Kapazitätsrechner

Der Rechner ist eine Microsoft Excel-Kalkulationstabelle. Die Felder für Ihre Eingaben sind orangefarben gehalten. Standardwerte werden in die Zellen (für Skype for Business Server 2015, 80.000-Benutzer in einem Pool mit zwölf Front-End-Servern, während für Skype for Business Server 2019, 106.000-Benutzer in einem Pool mit sechzehn Front-End-Servern) eingegeben, aber Sie sollten diese Werte in den Anforderungen Ihrer Organisation entsprechen.
  
Das Nutzungsmodell enthält die folgenden Abschnitte. Damit Sie Ihre Kapazitätsanforderungen berechnen können, geben Sie Daten gemäß der Beschreibung von oben nach unten zeilenweise ein: 
  
 **Chat und Anwesenheit (Instant Messaging/Presence, IM/P)**
  
- Geben Sie unter **Anzahl der Nutzer** die Anzahl von Nutzern ein, die gleichzeitig angemeldet sein werden. Diese Anzahl entspricht meist 80 % der Gesamtzahl der bereitgestellten Nutzer. In den meisten Situationen werden 100 % der gleichzeitigen Nutzer für Chat und Anwesenheit aktiviert. Der Standardwert ist 80.000 für Skype for Business Server 2015 und 106.000-Benutzer für Skype for Business Server 2019.
    
- **Durchschnittliche Anzahl von Kontakten in der Kontaktliste** gibt die Anzahl von Kontakten an, die zur Überprüfung Ihrer Systemanforderungen verwendet wird. Diese Anzahl ist festgelegt und sollte von Ihnen nicht geändert werden.
    
  **Enterprise-VoIP**
  
- Geben Sie in **Nutzer, für die Enterprise-VoIP aktiviert ist** den Prozentsatz Ihrer Nutzer an, für die Enterprise-VoIP aktiviert ist. Der Standardwert ist 60 %. 
    
- Geben Sie in **Durchschnittliche Anzahl von Anrufen pro Nutzer pro Stunde (Spitze)** die Anzahl von Anrufen pro Stunde ein, die Sie für durchschnittliche Nutzer als Teilnehmer zu Spitzenlastzeiten erwarten. Der Standardwert ist 4. 
    
- Geben Sie in **Prozentsatz der Anrufe, die Medienumgehung nutzen** den Prozentsatz der Anrufe ein, die von Ihren Nutzern getätigt, aber nicht über den Vermittlungsserver abgewickelt werden. Der Standardwert ist 65 %, könnte aber niedriger ausfallen, wenn Sie geografisch weit verteilt sind oder einen hohen Prozentsatz an Nutzern haben, die zu Hause arbeiten.
    
- Geben Sie in **Prozent der Sprachbenutzer, die an UC-PSTN-anrufen beteiligt**sind, den Prozentsatz der Anrufe Ihrer Organisation ein, bei denen es sich um UC-PSTN-Telefonanrufe handelt. Der Standardwert ist 60 %.
    
- **In Prozentsatz der VoIP-Nutzer, die an UC-UC-Anrufen beteiligt sind** ist der Prozentsatz der Nutzer enthalten, die zwar für Enterprise-VoIP, aber nur für UC-UC-Anrufe aktiviert sind. Diese Anzahl wird auf Basis des Werts berechnet, den Sie in **Prozentsatz der VoIP-Nutzer, die an UC-PSTN-Anrufen beteiligt sind** eingegeben haben. 
    
  **Konferenzen**
  
- Geben Sie in **Prozentsatz der Nutzer in gleichzeitigen Konferenzen** den Prozentsatz an Nutzern ein, die gleichzeitig an einer Konferenz teilnehmen werden. Der Standardwert ist 5 %. 
    
- Geben Sie in **Prozentsatz der Konferenzen nur mit Gruppen-Chat (kein VoIP)** den Prozentsatz an Konferenzen ein, für die ausschließlich Chat genutzt wird, d. h. Konferenzen ganz ohne Audio. Der Standardwert ist 10 %.
    
- Geben Sie in **Prozentsatz der Nutzer, die Einwahlkonferenzen verwenden** den Prozentsatz an Teilnehmern ein, die Einwahlkonferenzen gleichzeitig verwenden werden. Der Standardwert ist 15 %.
    
- Geben Sie in **Prozentsatz der Konferenzen mit VoIP** den Prozentsatz an Konferenzen ein, die Audio einschließen werden. 
    
  - Wenn 20 % Ihrer VoIP-Konferenzen auch normale Videoelemente umfassen, aktivieren Sie das Kontrollkästchen **Einschließlich Video (kein Multiview)**.
    
  - Wenn 20 % Ihrer Konferenzen auch Multiview-Videoelemente umfassen, aktivieren Sie das Kontrollkästchen **Einschließlich Multiview**.
    
  - Wenn 50% Ihrer VoIP-Konferenzen auch die Anwendungsfreigabe einschließen, aktivieren Sie das Kontrollkästchen **Anwendungsfreigabe einbeziehen** .
    
  - Wenn 20 % Ihrer VoIP-Konferenzen Datenuploads umfassen, zum Beispiel Microsoft PowerPoint-Präsentationen, aktivieren Sie das Kontrollkästchen **Einschließlich Webkonferenzen**.
    
  **Mobilität**
  
- Geben Sie in **Prozent der Benutzer, die für Mobilität aktiviert**sind, den Prozentsatz der Benutzer ein, die für die Verbindung mit Skype for Business Server mithilfe von mobilen Geräten aktiviert werden. Der Standardwert ist 40 %. 
    
Wenn Sie alle erforderlichen Informationen eingegeben haben, schätzt der Kapazitäts Rechner Ihre Anforderungen. Die gelben Zellen zeigen berechnete Werte für CPU-, Arbeitsspeicher-und Bandbreitenanforderungen basierend auf Tests, die in Skype for Business Server Performance Labs ausgeführt werden. Die Zahlen werden als Richtlinie bereitgestellt, nicht jede einzelne Variation wird getestet und validiert. Die folgenden Werte werden berechnet: 
  
- **Front-End-CPU:** Prozentsatz der CPU-Nutzung, wenn die gesamte Last von einem Front-End-Server verarbeitet wurde, der dieselben Spezifikationen hat wie der Server, der für die Tests verwendet wurde (siehe Beschreibung am Ende dieses Themas).
    
- **Netzwerk in MBit/s:** Bandbreitenanforderungen in Megabit pro Sekunde (MBit/s) für die entsprechende Arbeitsauslastung.
    
- **Arbeitsspeicher in GB:** Arbeitsspeicher in Gigabyte (GB), der für die entsprechende Arbeitsauslastung erforderlich ist.
    
In den grünen Zellen werden Empfehlungen für das Nutzungsmodell angezeigt, das Sie eingegeben haben. 
  
- **Gesamtzahl der Front-End-Server**: die Anzahl der erforderlichen physikalischen Server basiert auf dedizierten Servern, auf denen Skype for Business Server 2015 mit Dualprozessor, Hex-Core, 2.260 Megazyklen oder Skype for Business Server 2019 mit Intel Xeon E5-2673 v3, Dual Prozessor, Hex-Core.
    
    Es wird empfohlen, Hyperthreading zu aktivieren, denn damit lässt sich nachweislich die Leistung von Servern verbessern, die Audio/Video unterstützen.
    
- **Edgeserver:** Die Anzahl von erforderlichen Edgeservern. Diese Anzahl basiert auf 30 % aller gleichzeitigen Nutzer, die über die Edgeserver kommunizieren. Dieser Prozentsatz kann im Rechner nicht geändert werden. 
    
- **Speicher für die Dienste Archivierung/Aufzeichnung von Kommunikationsdatensätzen/Quality of Experience:** Die Anzahl von Speichern, die für Archivierungs- oder Überwachungsfeatures erforderlich sind, sofern diese in Ihrer Organisation aktiviert sind.
    
- **Erforderliche Back-End-Datenbankserver (erforderliche Pools):** Die Anzahl von Back-End-Datenbankservern, die erforderlich sind, damit die ausgewählte Auslastung unterstützt werden kann.
    
Die Zeile neben „Gesamtzahl der Front-End-Server“ enthält zusätzlich weitere Informationen zu der Last auf den Servern und im Netzwerk für alle geplanten Auslastungen zusammengenommen.
  
- **Durchschnittliche CPU-Auslastung:** Die durchschnittliche CPU-Nutzung pro Front-End-Server.
    
- **Netzwerk in MBit/s:** Die Bandbreitenzuteilung, die erforderlich ist, damit das von Ihnen eingegebene Nutzungsmodell unterstützt wird.
    
- **Arbeitsspeicher in GB:** Der Arbeitsspeicher in Gigabyte, der für jeden Front-End-Server erforderlich ist.
    
### <a name="adjusting-for-your-processors"></a>Anpassen an Ihre Prozessoren

Bei allen CPU-Nutzungszahlen in der Kalkulationstabelle wird davon ausgegangen, dass jeder Skype for Business Server 2015-Server über einen Dualprozessor, einen Hex-Core mit 2,26 GHz, mindestens 32 GB Arbeitsspeicher sowie 8 oder mehr 10.000-rpm-Festplattenlaufwerke mit mindestens 72 GB freiem Speicherplatz verfügt. Für jeden Skype for Business Server 2019-Server wird davon ausgegangen, dass jeder Server über einen Dualprozessor, einen Hex-Core mit Intel Xeon E5-2673 v3, mindestens 64 GB Arbeitsspeicher und 8 oder mehr 10.000-rpm-Festplattenlaufwerke mit mindestens 72 GB freiem Datenträger verfügt. Tempo.
  
Wenn Ihre Server andere Prozessoren haben, können Sie die Werte entsprechend Ihrer Hardware anpassen.
  
