---
title: Planen des Anruf Parks in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: Planung für den Parken von Anrufen in Skype for Business Server Enterprise-VoIP, wodurch Anrufe in Wartestellung gehalten und Anrufe an Abteilungen übertragen werden können. Hierzu gehören die Kapazitätsplanung, unterstützte Anrufe und unterstützte Clients.
ms.openlocfilehash: 3272efe89ac995b304d96ad7ce5660144641073b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277055"
---
# <a name="plan-for-call-park-in-skype-for-business"></a>Planen des Anruf Parks in Skype for Business
 
Planung für den Parken von Anrufen in Skype for Business Server Enterprise-VoIP, wodurch Anrufe in Wartestellung gehalten und Anrufe an Abteilungen übertragen werden können. Hierzu gehören die Kapazitätsplanung, unterstützte Anrufe und unterstützte Clients.
  
Mit der Anwendung "Anruf parken" können Enterprise-VoIP-Benutzer die folgenden Aktionen ausführen:
  
- Halten eines Anrufs und anschließendes Entgegennehmen des Anrufs am selben oder an einem anderen Telefon.
    
- Halten eines Anrufs, um ihn an eine Abteilung oder einen allgemeinen Bereich zu übergeben (z. B. die Vertriebsabteilung oder ein Lagerort mit einem Telefon im öffentlichen Bereich).
    
- Halten eines Anrufs, um weitere Anrufe an einem Telefon entgegennehmen zu können.
    
Wenn ein Benutzer einen Anruf parkt, übernimmt Skype for Business Server den Anruf an eine temporäre Nummer, die so genannte Orbit, in der der Anruf gehalten wird, bis er abgerufen wird, oder es ist ein Timeout. Skype for Business Server sendet die Umlaufbahn an den Benutzer, der den Anruf abgestellt hat. Zum Wiederaufnehmen des geparkten Anrufs kann der Benutzer die Orbitnummer wählen oder auf den Orbitlink oder die Schaltfläche im Fenster „Unterhaltung“ klicken. 
  
Der Benutzer, der einen Anruf geparkt hat, kann einen anderen Benutzer mithilfe eines externen Mechanismus (beispielsweise über eine Sofortnachricht oder ein Paging-System) über die Orbitnummer informieren, damit dieser Benutzer den Anruf entgegennehmen kann. Der Benutzer, der den Anruf geparkt hat, kann das Fenster „Unterhaltung“ geöffnet lassen, um eine Benachrichtigung zu erhalten, sobald der Anruf entgegengenommen wurde.
  
Da die Umlaufbahn Bereiche global eindeutig sind, ist es möglich, Anrufe von jeder Skype for Business Server-Website oder einem PBX-Telefon abzurufen, wenn Routing entsprechend konfiguriert ist. Wenn der Anruf innerhalb einer konfigurierbaren Zeitdauer nicht wiederaufgenommen wird, wird er erneut an den Benutzer zurückgegeben, der den Anruf geparkt hat. Wenn dieser Benutzer den Anruf nicht beantwortet, wird er an ein Fallbackziel übergeben (z. B. einen Agent), sofern dies konfiguriert wurde. Sie können konfigurieren, wie oft das Telefon erneut läutet (ein- bis zehnmal), bevor der Anruf weitergeleitet wird. Wenn ein weitergeleiteter Anruf nicht entgegengenommen wird, wird die Verbindung unterbrochen. Wenn der Anruf entgegengenommen oder die Verbindung unterbrochen wird, wird der Orbit erneut freigegeben.
  
Wenn Sie die Funktion zum Parken von Anrufen bereitstellen, müssen Sie Durchwahlnummernbereiche zum Parken von Anrufen reservieren. Bei diesen Durchwahlnummern muss es sich um virtuelle Durchwahlnummern handeln, also solche, denen kein Benutzer oder Telefon zugewiesen ist. Anschließend konfigurieren Sie die Orbittabelle für das Parken von Anrufen mit den Durchwahlnummernbereichen und geben an, welcher Anwendungsdienst die Anwendung zum Parken von Anrufen hostet, die die einzelnen Bereiche verarbeitet. Jeder Front-End-Pool verfügt über eine Anruf Park Tabelle auf dem entsprechenden Back-End-Server, der zum Verwalten von Anrufen dient, die auf dem Pool abgestellt werden. Die Liste der Umlaufbahn Bereiche wird im zentralen Verwaltungsspeicher gespeichert und zum Weiterleiten von Umlaufbahnen an den Ziel Pool verwendet. Jeder Skype for Business-Server Pool, in dem die Anwendung für das Parken von Anrufen bereitgestellt und konfiguriert ist, kann einen oder mehrere Umlaufbahn Bereiche aufweisen. Umlaufbahn Bereiche müssen in der Skype for Business Server-Bereitstellung global eindeutig sein. 
  
Sie können darüber hinaus weitere Einstellungen für das Parken von Anrufen konfigurieren, wie z. B., an welches Ziel Anrufe bei einem Timeout umgeleitet werden und ob für den Anrufer Musik wiedergegeben wird, während der Anruf geparkt ist. Außerdem können Sie die Musikdatei angeben, die beim Parken des Anrufs wiedergegeben wird.
  
> [!NOTE]
> Angepasste Musik-in-situ-Dateien für den Parken von Anrufen werden nicht im Rahmen des Disaster Recovery-Prozesses von Skype for Business Server gesichert und gehen verloren, wenn die Dateien, die in den Pool hochgeladen wurden, beschädigt, beschädigt oder gelöscht wurden. Bewahren Sie stets eine separate Sicherungskopie der für geparkte Anrufe hochgeladenen angepassten Musikdateien auf. 
  
Die Anwendung zum Parken von Anrufen ist eine Enterprise-VoIP-Komponente. Wenn Sie Enterprise-VoIP bereitstellen, wird die Anwendung für den Anruf Park automatisch installiert und aktiviert. Bevor Sie den Anruf Park verwenden können, muss der Enterprise Voice-Administrator ihn aber über die VoIP-Richtlinie konfigurieren und für die Benutzer aktivieren.
  
## <a name="deployment-and-requirements"></a>Bereitstellung und Anforderungen

Die Anwendung Parken wird automatisch installiert, wenn Sie Enterprise-VoIP bereitstellen. Sie aktivieren den Anruf Park durch Konfigurieren der VoIP-Richtlinie.
  
### <a name="software-requirements"></a>Softwareanforderungen

Auf allen Front-End-Servern und Standard Edition-Servern, auf denen der Anruf Park bereitgestellt wird, muss die Windows Media-Format Laufzeit für Server mit Windows Server 2008 R2 oder Microsoft Media Foundation für Server mit Windows Server 2012 oder Windows Server installiert sein. 2012 R2. Für Windows Server 2008 R2 wird die Windows Media-Format Laufzeit als Teil der Windows-Desktop Oberfläche installiert. Windows Media Format Runtime oder Microsoft Media Foundation ist für Windows Media Audio-Dateien (WMA) erforderlich, in denen Park Wiedergaben für Musik im Wartebereich aufgerufen werden.
  
### <a name="port-requirements"></a>Portanforderungen

Die Anwendung für den Anruf Park verwendet **Port 5075** für SIP-Abhör Anforderungen.
    
> [!NOTE]
> Dieser Port ist die Standardeinstellung, die Sie mit dem Cmdlet **Set-CsApplicationServer** ändern können. Details zu diesem Cmdlet finden Sie in der Dokumentation zur lync Server-Verwaltungsshell.
  
### <a name="audio-file-requirements"></a>Anforderungen für Audiodateien

Die Anwendung "Parken" unterstützt nur WMA-Dateien (Windows Media Audio) für Musik in Wartestellung. Sie können den Microsoft Expression Encoder 4 verwenden, um Dateien für Musik in Wartestellung anzupassen. Informationen zum Herunterladen von Expression Encoder 4 finden Sie unter ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843). Verwenden Sie das Tool, um die Datei in ein WMA-Format umzuwandeln. Das empfohlene Format für Music-on-halten-Dateien im Parken von anrufen ist Media Audio 9, 44 kHz, 16 Bits, Mono, CBR, 32 Kbit/s.
  
> [!NOTE]
> Die konvertierte Datei wird über das Telefon nur mit 16 kHz abgespielt, auch wenn sie mit 44 kHz aufgezeichnet wurde. 
  
## <a name="supported-clients-and-calls"></a>Unterstützte Clients und Anrufe

Die folgenden Clients und Anrufarten werden für den Parken von Anrufen unterstützt.
  
### <a name="clients-supported-for-parking-calls"></a>Für das Parken von Anrufen unterstützte Clients

Anrufe von IP-, Nebenstellen-, Festnetz- oder Mobiltelefonen können geparkt werden.
  
> [!NOTE]
> Nur Audioanrufe können geparkt werden. Das Parken von Chatnachrichten und Konferenzen ist nicht möglich. 
  
Die folgenden Clients können den Anruf Park zum Parken von Anrufen verwenden:
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010-Vermittlung
    
- Lync Phone Edition
    
> [!NOTE]
> Mobiltelefone können den Anruf Park nicht zum Parken von Anrufen verwenden. 
  
### <a name="clients-supported-for-retrieving-calls"></a>Für das Wiederaufnehmen geparkter Anrufe unterstützte Clients

Orbitbereiche werden als Blöcke virtueller Durchwahlnummern (Durchwahlnummern, denen kein Benutzer oder Telefon zugewiesen ist) konfiguriert. Wenn Sie Orbits als virtuelle Durchwahlnummern konfigurieren, können Mobil- und Festnetztelefone keine geparkten Anrufe wiederaufnehmen.
  
Das Wiederaufnehmen geparkter Anrufe durch Partnerbenutzer ist nicht möglich.
  
Die folgenden Clients können Anrufe abrufen, die im Park des Anrufs abgestellt sind:
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010-Vermittlung
    
- Lync Phone Edition
    
- IP-Telefone in öffentlichen Bereichen
    
- Nicht-IP-Telefone, die mit der Skype for Business Server-Infrastruktur verbunden sind, einschließlich Telefone im öffentlichen Bereich und Private Branch Exchange (PBX)-Telefone
    
## <a name="call-park-capacity-planning"></a>Kapazitätsplanung für das Parken von Anrufen

In der folgenden Tabelle wird das Benutzermodell des Anruf Parks beschrieben, das Sie als Grundlage für die Kapazitäts Planungsanforderungen verwenden können.
  
> [!IMPORTANT]
> Beachten Sie, dass für die Planung von Disaster Recovery-Kapazität jeder Pool eines gekoppelten Pools in der Lage sein sollte, die Arbeitslasten für die Dienste des Anruf Parks in beiden Pools zu behandeln. 
  
**Benutzermodell der Funktion zum Parken von Anrufen**

|**Metrik**|**Pro Front-End <br/> -Pool (mit 8 Front-End-Servern)**|**Pro Standard Edition-Server**|
|:-----|:-----|:-----|
|Rate für das Parken von Anrufen  <br/> |8 pro Minute  <br/> |1 pro Minute  <br/> |
|Rate für das Abrufen geparkter Anrufe  <br/> |8 pro Minute  <br/> |1 pro Minute  <br/> |
|Durchschnittliche Parkdauer  <br/> |60 Sekunden  <br/> |60 Sekunden  <br/> |
   

