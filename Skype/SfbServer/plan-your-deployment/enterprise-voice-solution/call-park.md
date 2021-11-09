---
title: Planen des Parkens von Anrufen in Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: Planung des Parkens von Anrufen in Skype for Business Server Enterprise-VoIP, wodurch Anrufe gehalten und an Abteilungen übertragen werden können. Umfasst Kapazitätsplanung, unterstützte Anrufe und unterstützte Clients.
ms.openlocfilehash: 29ca14f85aeccaa8394ede4420c66af77e5c66c8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60839837"
---
# <a name="plan-for-call-park-in-skype-for-business"></a>Planen des Parkens von Anrufen in Skype for Business
 
Planung des Parkens von Anrufen in Skype for Business Server Enterprise-VoIP, wodurch Anrufe gehalten und an Abteilungen übertragen werden können. Umfasst Kapazitätsplanung, unterstützte Anrufe und unterstützte Clients.
  
Die Anwendung zum Parken von Anrufen ermöglicht Enterprise-VoIP Benutzern Folgendes:
  
- Halten Sie einen Anruf an, und rufen Sie den Anruf dann vom gleichen telefon oder einem anderen Telefon ab.
    
- Halten Sie einen Anruf, um ihn an eine Abteilung oder einen allgemeinen Bereich zu übertragen (z. B. an eine Vertriebsabteilung oder ein Lager, in dem ein Telefon für gemeinsame Bereiche vorhanden ist).
    
- Halten Sie einen Anruf in die Warteschleife, und lassen Sie das ursprüngliche Telefon für andere Anrufe kostenlos.
    
Wenn ein Benutzer einen Anruf anruft, überträgt Skype for Business Server den Anruf an eine temporäre Nummer, die als Orbit bezeichnet wird, an der der Anruf gehalten wird, bis er entgegennimmt oder ein Zeitüberschreitung aufgetreten ist. Skype for Business Server sendet den Orbit an den Benutzer, der den Anruf geparkt hat. Um den geparkten Anruf abzurufen, kann der Benutzer die Orbitnummer wählen oder auf die Orbitverbindung oder -schaltfläche im Unterhaltungsfenster klicken. 
  
Der Benutzer, der einen Anruf geparkt hat, kann jemanden über einen externen Mechanismus, z. B. Chatnachrichten oder ein Auslagerungssystem, benachrichtigen, um die Orbitnummer an eine andere Person zu kommunizieren. Der Benutzer, der den Anruf geparkt hat, kann das Unterhaltungsfenster geöffnet lassen, um eine Benachrichtigung zu erhalten, wenn der Anruf abgerufen wird.
  
Da orbit ranges are globally unique, it is possible to retrieve calls from any Skype for Business Server site or PBX phone if routing is configured appropriately. Wenn niemand den Anruf innerhalb einer konfigurierbaren Zeit abruft, wird der Anruf an die Person zurückgerufen, die ihn geparkt hat. Wenn diese Person den Rückruf nicht entgegennimmt, wird der Anruf an ein Fallbackziel weitergeleitet, z. B. an einen Operator, sofern dies konfiguriert ist. Sie können konfigurieren, wie oft der Anruf zurückruft, bevor er von 1 bis 10 Mal weitergeleitet wird. Wenn niemand einen weitergeleiteten Anruf entgegennimmt, wird der Anruf getrennt. Der Orbit wird freigegeben, wenn der Anruf abgerufen oder getrennt wird.
  
Wenn Sie das Parken von Anrufen bereitstellen, müssen Sie Bereiche von Durchwahlnummern für das Parken von Anrufen reservieren. Diese Erweiterungen müssen virtuelle Erweiterungen sein: Erweiterungen, denen kein Benutzer oder Telefon zugewiesen ist. Anschließend konfigurieren Sie die Orbittabelle für das Parken von Anrufen mit den Erweiterungsnummernbereichen und geben an, welcher Anwendungsdienst die Anwendung zum Parken von Anrufen hostet, die die einzelnen Bereiche verarbeitet. Jeder Front-End-Pool verfügt über eine Tabelle zum Parken von Anrufen auf dem entsprechenden Back-End-Server, der zum Verwalten von Anrufen verwendet wird, die im Pool geparkt sind. Die Liste der Orbitbereiche wird im zentralen Verwaltungsspeicher gespeichert und zum Weiterleiten von Orbits an den Zielpool verwendet. Jeder Skype for Business Server Pool, in dem die Anwendung zum Parken von Anrufen bereitgestellt und konfiguriert ist, kann einen oder mehrere Orbitbereiche aufweisen. Orbitbereiche müssen in der Skype for Business Server Bereitstellung global eindeutig sein. 
  
Sie konfigurieren auch andere Einstellungen für das Parken von Anrufen, z. B. wo Anrufe umgeleitet werden, wenn ein Timeout auftritt und ob die Person auf dem Telefon beim Parken Musik hört. Sie können auch die Musikdatei angeben, die wiedergegeben werden soll, während der Anruf gehalten wird.
  
> [!NOTE]
> Angepasste Wartemusikdateien für das Parken von Anrufen werden nicht als Teil des Skype for Business Server Notfallwiederherstellungsprozesses gesichert und gehen verloren, wenn die in den Pool hochgeladenen Dateien beschädigt, beschädigt oder gelöscht werden. Behalten Sie immer eine separate Sicherungskopie der angepassten Wartemusikdateien bei, die Sie für das Parken von Anrufen hochgeladen haben. 
  
Die Anwendung zum Parken von Anrufen ist eine Komponente von Enterprise-VoIP. Wenn Sie Enterprise-VoIP bereitstellen, wird die Anwendung zum Parken von Anrufen automatisch installiert und aktiviert. Bevor Sie das Parken von Anrufen verwenden können, muss der Enterprise-VoIP-Administrator sie jedoch konfigurieren und für Benutzer über eine VoIP-Richtlinie aktivieren.
  
## <a name="deployment-and-requirements"></a>Bereitstellung und Anforderungen

Die Anwendung zum Parken von Anrufen wird automatisch installiert, wenn Sie Enterprise-VoIP bereitstellen. Sie aktivieren das Parken von Anrufen, indem Sie die VoIP-Richtlinie konfigurieren.
  
### <a name="software-requirements"></a>Softwareanforderungen

Auf allen Front-End-Servern und Standard Edition Servern, auf denen das Parken von Anrufen bereitgestellt wird, muss die Windows Media Format Runtime für Server mit Windows Server 2008 R2 oder Microsoft Media Foundation für Server mit Windows Server 2012 oder Windows Server 2012 R2 installiert sein. . For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience. Windows Die Medienformatlaufzeit oder Microsoft Media Foundation ist für Windows WMA-Dateien (Media Audio) erforderlich, die für die Wartemusik wiedergegeben werden.
  
### <a name="port-requirements"></a>Portanforderungen

Die Anwendung zum Parken von Anrufen verwendet **Port 5075**  für SIP-Überwachungsanforderungen.
    
> [!NOTE]
> Dieser Port ist die Standardeinstellung, die Sie mit dem Cmdlet **Set-CsApplicationServer** ändern können. Ausführliche Informationen zu diesem Cmdlet finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.
  
### <a name="audio-file-requirements"></a>Audiodateianforderungen

Die Anwendung zum Parken von Anrufen unterstützt nur Windows WMA-Dateien (Media Audio) für Wartemusik. Sie können Dateien für Wartemusik mit Microsoft Expression Encoder 4 anpassen. Informationen zum Herunterladen von Expression Encoder 4 finden Sie unter ["Expression Encoder 4".](https://go.microsoft.com/fwlink/p/?linkId=202843) Verwenden Sie das Tool, um die Datei in ein WMA-Format zu konvertieren. Das empfohlene Format für Wartemusikdateien für die Anwendung zum Parken von Anrufen ist Media Audio 9, 44 kHz, 16 Bit, Mono, CBR oder 32 KBit/s.
  
> [!NOTE]
> Die konvertierte Datei wird über das Telefon nur mit 16 kHz abgespielt, auch wenn diese mit 44 kHz aufgezeichnet wurde. 
  
## <a name="supported-clients-and-calls"></a>Unterstützte Clients und Anrufe

Die folgenden Clients und Anruftypen werden für das Parken von Anrufen unterstützt.
  
### <a name="clients-supported-for-parking-calls"></a>Für das Parken von Anrufen unterstützte Clients

Anrufe von IP-, Nebenstellen-, Festnetz- oder Mobiltelefonen können geparkt werden.
  
> [!NOTE]
> Nur Audioanrufe können geparkt werden. Das Parken von Chatnachrichten und Konferenzen ist nicht möglich. 
  
Die folgenden Clients können das Parken von Anrufen zum Parken von Anrufen verwenden:
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
> [!NOTE]
> Mobiltelefone können das Parken von Anrufen nicht zum Parken von Anrufen verwenden. 
  
### <a name="clients-supported-for-retrieving-calls"></a>Für das Wiederaufnehmen geparkter Anrufe unterstützte Clients

Orbitbereiche werden als Blöcke virtueller Durchwahlnummern (Durchwahlnummern, denen kein Benutzer oder Telefon zugewiesen ist) konfiguriert. Wenn Sie Orbits als virtuelle Durchwahlnummern konfigurieren, können Mobil- und Festnetztelefone keine geparkten Anrufe wiederaufnehmen.
  
Das Wiederaufnehmen geparkter Anrufe durch Partnerbenutzer ist nicht möglich.
  
Die folgenden Clients können Anrufe abrufen, die beim Parken von Anrufen geparkt sind:
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
- IP-Telefone in öffentlichen Bereichen
    
- Nicht-IP-Telefone, die mit der Skype for Business Server-Infrastruktur verbunden sind, einschließlich Telefone für öffentliche Bereiche und Nebenstellenanlagentelefone
    
## <a name="call-park-capacity-planning"></a>Kapazitätsplanung für das Parken von Anrufen

In der folgenden Tabelle wird das Benutzermodell für das Parken von Anrufen beschrieben, das Sie als Grundlage für die Anforderungen an die Kapazitätsplanung verwenden können.
  
> [!IMPORTANT]
> Beachten Sie, dass bei der Kapazitätsplanung für die Notfallwiederherstellung jeder Pool eines gepaarten Pools in der Lage sein sollte, die Workloads für Dienste zum Parken von Anrufen in beiden Pools zu verarbeiten. 
  
**Benutzermodell der Funktion zum Parken von Anrufen**

|**Metrik**|**Pro Front-End-Pool  <br/>  (mit 8 Front-End-Servern)**|**Pro Standard Edition-Server**|
|:-----|:-----|:-----|
|Rate für das Parken von Anrufen  <br/> |8 pro Minute  <br/> |1 pro Minute  <br/> |
|Rate für das Abrufen geparkter Anrufe  <br/> |8 pro Minute  <br/> |1 pro Minute  <br/> |
|Durchschnittliche Parkdauer  <br/> |60 Sekunden  <br/> |60 Sekunden  <br/> |
   

