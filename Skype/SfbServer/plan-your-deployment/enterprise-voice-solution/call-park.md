---
title: Planen des Parkens von Anrufen in Skype for Business
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: Planung für das Parken von Anrufen in Skype für Business Server Enterprise-VoIP, können die für Anrufe, die auf halten und Weiterleiten von Anrufen zu Abteilungen eingefügt. Hierzu gehören die Kapazitätsplanung, unterstützte Anrufe und unterstützte Clients.
ms.openlocfilehash: a675100f8b40e1ab293c0240ea0acbe3beb7fa27
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20988550"
---
# <a name="plan-for-call-park-in-skype-for-business"></a>Planen des Parkens von Anrufen in Skype for Business
 
Planung für das Parken von Anrufen in Skype für Business Server Enterprise-VoIP, können die für Anrufe, die auf halten und Weiterleiten von Anrufen zu Abteilungen eingefügt. Hierzu gehören die Kapazitätsplanung, unterstützte Anrufe und unterstützte Clients.
  
Die Anwendung zum Parken kann Enterprise-VoIP-Benutzer folgende Aktionen ausführen:
  
- Halten eines Anrufs und anschließendes Entgegennehmen des Anrufs am selben oder an einem anderen Telefon.
    
- Halten eines Anrufs, um ihn an eine Abteilung oder einen allgemeinen Bereich zu übergeben (z. B. die Vertriebsabteilung oder ein Lagerort mit einem Telefon im öffentlichen Bereich).
    
- Halten eines Anrufs, um weitere Anrufe an einem Telefon entgegennehmen zu können.
    
Wenn ein Benutzer Parks überträgt Gespräch Skype für Business Server den Anruf an eine temporäre Zahl, eine Orbit aufgerufen wird, in dem der Anruf gespeichert, bis es abgerufen wird, oder das Zeitlimit überschritten. Skype für Business Server sendet den Orbit, dem Benutzer, der den Anruf geparkt. Zum Wiederaufnehmen des geparkten Anrufs kann der Benutzer die Orbitnummer wählen oder auf den Orbitlink oder die Schaltfläche im Fenster „Unterhaltung“ klicken. 
  
Der Benutzer, der einen Anruf geparkt hat, kann einen anderen Benutzer mithilfe eines externen Mechanismus (beispielsweise über eine Sofortnachricht oder ein Paging-System) über die Orbitnummer informieren, damit dieser Benutzer den Anruf entgegennehmen kann. Der Benutzer, der den Anruf geparkt hat, kann das Fenster „Unterhaltung“ geöffnet lassen, um eine Benachrichtigung zu erhalten, sobald der Anruf entgegengenommen wurde.
  
Da orbitbereiche global eindeutig sind, ist es möglich, Anrufe von jeder Skype für Business Server-Website oder PBX-Telefon abrufen, wenn routing entsprechend konfiguriert ist. Wenn der Anruf innerhalb einer konfigurierbaren Zeitdauer nicht wiederaufgenommen wird, wird er erneut an den Benutzer zurückgegeben, der den Anruf geparkt hat. Wenn dieser Benutzer den Anruf nicht beantwortet, wird er an ein Fallbackziel übergeben (z. B. einen Agent), sofern dies konfiguriert wurde. Sie können konfigurieren, wie oft das Telefon erneut läutet (ein- bis zehnmal), bevor der Anruf weitergeleitet wird. Wenn ein weitergeleiteter Anruf nicht entgegengenommen wird, wird die Verbindung unterbrochen. Wenn der Anruf entgegengenommen oder die Verbindung unterbrochen wird, wird der Orbit erneut freigegeben.
  
Wenn Sie die Funktion zum Parken von Anrufen bereitstellen, müssen Sie Durchwahlnummernbereiche zum Parken von Anrufen reservieren. Bei diesen Durchwahlnummern muss es sich um virtuelle Durchwahlnummern handeln, also solche, denen kein Benutzer oder Telefon zugewiesen ist. Anschließend konfigurieren Sie die Orbittabelle für das Parken von Anrufen mit den Durchwahlnummernbereichen und geben an, welcher Anwendungsdienst die Anwendung zum Parken von Anrufen hostet, die die einzelnen Bereiche verarbeitet. Jeder Front-End-Pool verfügt über die Tabelle zum Parken von Anrufen auf den entsprechenden Back End-Server, der verwendet wird, um Anrufe zu verwalten, die im Pool geparkt werden. Die Liste der orbitbereiche in der zentralen gespeichert ist speichern und wird verwendet, um Orbits auf den Zielpool weitergeleitet. Jede Skype für Business Server Pool, in dem die Anwendung zum Parken bereitgestellt und konfiguriert ist, kann eine oder mehrere orbitbereiche haben. Orbitbereiche müssen für die Skype für Business Server-Bereitstellung global eindeutig sein. 
  
Sie können darüber hinaus weitere Einstellungen für das Parken von Anrufen konfigurieren, wie z. B., an welches Ziel Anrufe bei einem Timeout umgeleitet werden und ob für den Anrufer Musik wiedergegeben wird, während der Anruf geparkt ist. Außerdem können Sie die Musikdatei angeben, die beim Parken des Anrufs wiedergegeben wird.
  
> [!NOTE]
> Benutzerdefinierte Musik halten-Dateien für das Parken werden nicht als Teil der Skype für notfallwiederherstellungsprozess Business Server gesichert und deshalb verloren gehen, wenn die Dateien auf den Pool hochgeladen beschädigt, beschädigt oder gelöscht werden. Bewahren Sie stets eine separate Sicherungskopie der für geparkte Anrufe hochgeladenen angepassten Musikdateien auf. 
  
Die Anwendung zum Parken von Anrufen ist eine Enterprise-VoIP-Komponente. Wenn Sie Enterprise-VoIP bereitstellen, wird die Anwendung zum Parken installiert und automatisch aktiviert. Vor der Verwendung des Parkens von Anrufen jedoch muss der Enterprise-VoIP-Administrator konfiguriert wird und für Benutzer über VoIP-Richtlinie zu aktivieren.
  
## <a name="deployment-and-requirements"></a>Bereitstellung und Anforderungen

Die Anwendung zum Parken wird bei der Bereitstellung von Enterprise-VoIP automatisch installiert. Konfigurieren von VoIP-Richtlinie aktivieren Sie das Parken von Anrufen.
  
### <a name="software-requirements"></a>Softwareanforderungen

Alle Front-End-Servern und Standard Edition-Servern in der Parken bereitgestellt wird, müssen die Windows Media Format-Laufzeitkomponente für Server mit Windows Server 2008 R2 oder Microsoft Media Foundation für Server mit Windows Server 2012 oder Windows Server installiert haben 2012 R2. Windows Media Format-Laufzeitkomponente ist für Windows Server 2008 R2 als Teil des Windows Desktop Experience installiert. Windows Media Format-Laufzeitkomponente oder Microsoft Media Foundation ist erforderlich für Windows Media Audio (WMA)-Dateien, die zum Parken von Anrufen wiedergegeben wird für die Musik in der Warteschleife.
  
### <a name="port-requirements"></a>Portanforderungen

Die Anwendung zum Parken von Anrufen verwendet **Port 5075** für SIP-überwachungsanforderungen verwendet.
    
> [!NOTE]
> Dieser Port ist eine Standardeinstellung, die Sie mit dem Cmdlet **Set-CsApplicationServer** ändern können. Ausführliche Informationen zu diesem Cmdlet finden Sie unter der Lync Server-Verwaltungsshell-Dokumentation.
  
### <a name="audio-file-requirements"></a>Anforderungen für Audiodateien

Halten Sie das Parken von Anrufen, die Anwendung auf nur Windows Media Audio (WMA) Dateien für die Musik unterstützt. Der Microsoft Ausdruck Encoder 4 können Sie Dateien für die Musik in der Warteschleife anpassen. Informationen zum Herunterladen von Expression Encoder 4 finden Sie unter ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843). Verwenden Sie das Tool, um die Datei in ein WMA-Format zu konvertieren. Das empfohlene Format für das Parken von Anrufen Musik halten Dateien ist Media Audio 9, 44 kHz, 16 Bit, Mono, CBR 32 Kbit/s.
  
> [!NOTE]
> Die konvertierte Datei wird über das Telefon nur mit 16 kHz abgespielt, auch wenn sie mit 44 kHz aufgezeichnet wurde. 
  
## <a name="supported-clients-and-calls"></a>Unterstützte Clients und Anrufe

Die folgenden Clients und Anruftypen werden für das Parken unterstützt.
  
### <a name="clients-supported-for-parking-calls"></a>Für das Parken von Anrufen unterstützte Clients

Anrufe von IP-, Nebenstellen-, Festnetz- oder Mobiltelefonen können geparkt werden.
  
> [!NOTE]
> Nur Audioanrufe können geparkt werden. Das Parken von Chatnachrichten und Konferenzen ist nicht möglich. 
  
Die folgenden Clients können zum Parken von Anrufen für das Parken von Anrufen:
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
> [!NOTE]
> Mobiltelefone können nicht zum Parken von Anrufen für das Parken von Anrufen verwenden. 
  
### <a name="clients-supported-for-retrieving-calls"></a>Für das Wiederaufnehmen geparkter Anrufe unterstützte Clients

Orbitbereiche werden als Blöcke virtueller Durchwahlnummern (Durchwahlnummern, denen kein Benutzer oder Telefon zugewiesen ist) konfiguriert. Wenn Sie Orbits als virtuelle Durchwahlnummern konfigurieren, können Mobil- und Festnetztelefone keine geparkten Anrufe wiederaufnehmen.
  
Das Wiederaufnehmen geparkter Anrufe durch Partnerbenutzer ist nicht möglich.
  
Die folgenden Clients können Anrufe wiederaufnehmen, die auf das Parken von Anrufen geparkt wurden:
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
- IP-Telefone in öffentlichen Bereichen
    
- Nicht-IP-Telefone, die mit der Skype für Business Server-Infrastruktur, einschließlich Telefone in öffentlichen Bereichen und private Branch Exchange, (Nebenstellenanlage PBX) verbunden sind
    
## <a name="call-park-capacity-planning"></a>Kapazitätsplanung für das Parken von Anrufen

Die folgende Tabelle beschreibt das Benutzermodell für das Parken von Anrufen, das Sie als Grundlage für Anforderungen an die kapazitätsplanung verwenden können.
  
> [!IMPORTANT]
> Beachten Sie, dass die kapazitätsplanung, für die Disaster Recovery jeder Pool eines gekoppelten Pools die Arbeitslast für das Parken von Anrufen Dienste in beiden Pools kann soll beibehalten. 
  
**Benutzermodell der Funktion zum Parken von Anrufen**

|**Metrik**|**Pro Front-End-Pool <br/> (mit 8 Front-End-Servern)**|**Pro Standard Edition-Server**|
|:-----|:-----|:-----|
|Rate für das Parken von Anrufen  <br/> |8 pro Minute  <br/> |1 pro Minute  <br/> |
|Rate für das Abrufen geparkter Anrufe  <br/> |8 pro Minute  <br/> |1 pro Minute  <br/> |
|Durchschnittliche Parkdauer  <br/> |60 Sekunden  <br/> |60 Sekunden  <br/> |
   

