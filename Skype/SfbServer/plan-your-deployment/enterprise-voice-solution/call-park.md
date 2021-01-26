---
title: Planen des Parkens von Anrufen in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: Planen des Parkens von Anrufen in Skype for Business Server Enterprise-VoIP, wodurch Anrufe in der Warteschleife gespeichert und Anrufe an Abteilungen übertragen werden können. Umfasst Kapazitätsplanung, unterstützte Anrufe und unterstützte Clients.
ms.openlocfilehash: c324e8d61f6d0e9e67870f05597a9157965a3eb3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825925"
---
# <a name="plan-for-call-park-in-skype-for-business"></a>Planen des Parkens von Anrufen in Skype for Business
 
Planen des Parkens von Anrufen in Skype for Business Server Enterprise-VoIP, wodurch Anrufe in der Warteschleife gespeichert und Anrufe an Abteilungen übertragen werden können. Umfasst Kapazitätsplanung, unterstützte Anrufe und unterstützte Clients.
  
Mit der Anwendung zum Parken von Anrufen Enterprise-VoIP Benutzer folgende Aufgaben:
  
- Halten Sie einen Anruf in der Warteschleife, und rufen Sie dann den Anruf von demselben Oder einem anderen Telefon ab.
    
- Halten Sie einen Anruf in der Warteschleife, um ihn an eine Abteilung oder einen allgemeinen Bereich zu übertragen (z. B. an eine Vertriebsabteilung oder ein Lager, in dem sich ein Telefon in einem gemeinsamen Bereich befindet).
    
- Halten Sie einen Anruf in der Warteschleife, und halten Sie das ursprüngliche Anrufbeantwortungstelefon für andere Anrufe frei.
    
Wenn ein Benutzer einen Anruf parkt, überträgt Skype for Business Server den Anruf an eine temporäre Nummer, die als Orbit bezeichnet wird, an der der Anruf gehalten wird, bis er abgerufen wird oder ein Zeitsendzeitplan erreicht wird. Skype for Business Server sendet den Orbit an den Benutzer, der den Anruf geparkt hat. Um den geparkten Anruf abzurufen, kann der Benutzer die Orbitnummer wählen oder im Unterhaltungsfenster auf den Orbitlink oder die Schaltfläche klicken. 
  
Der Benutzer, der einen Anruf geparkt hat, kann eine Person über einen externen Mechanismus, z. B. Chat oder Pagingsystem, benachrichtigen, um die Orbitnummer an eine andere Person weiter zu kommunizieren. Der Benutzer, der den Anruf geparkt hat, kann das Unterhaltungsfenster geöffnet lassen, um eine Benachrichtigung zu erhalten, wenn der Anruf abgerufen wird.
  
Da Orbitbereiche global eindeutig sind, ist es möglich, Anrufe von einem beliebigen Skype for Business Server-Standort oder Nebenstellentelefon abzurufen, wenn das Routing entsprechend konfiguriert ist. Wenn der Anruf nicht innerhalb einer konfigurierbaren Zeit abgerufen wird, wird der Anruf an die Person zurückrufen, die ihn geparkt hat. Wenn diese Person den Rückruf nicht beantwortet, wird der Anruf an ein Fallbackziel, z. B. an eine Telefongesellschaft, übergeben, falls dies konfiguriert ist. Sie können die Anzahl der Rückrufe konfigurieren, bevor der Anruf ein- bis zehnmal übertragen wird. Wenn ein durchgeschalteter Anruf nicht beantwortet wird, wird der Anruf getrennt. Der Orbit wird beim Abrufen oder Trennen des Anrufs wieder freigeschaltet.
  
Wenn Sie das Parken von Anrufen bereitstellen, müssen Sie Durchwahlnummernbereiche für das Parken von Anrufen reservieren. Diese Erweiterungen müssen virtuelle Erweiterungen sein: Erweiterungen, denen kein Benutzer oder Telefon zugewiesen ist. Anschließend konfigurieren Sie die Orbittabelle für das Parken von Anrufen mit den Durchwahlnummernbereichen und geben an, welcher Anwendungsdienst die Anwendung zum Parken von Anrufen hostet, die jeden Bereich verarbeitet. Jeder Front-End-Pool verfügt über eine Tabelle zum Parken von Anrufen auf dem entsprechenden Back-End-Server, der zum Verwalten von Anrufen verwendet wird, die im Pool geparkt werden. Die Liste der Orbitbereiche wird im zentralen Verwaltungsspeicher gespeichert und zum Routen von Orbits an den Zielpool verwendet. Jeder Skype for Business Server-Pool, in dem die Anwendung zum Parken von Anrufen bereitgestellt und konfiguriert ist, kann einen oder mehrere Orbitbereiche haben. Orbitbereiche müssen global innerhalb der Skype for Business Server-Bereitstellung eindeutig sein. 
  
Darüber hinaus konfigurieren Sie andere Einstellungen für das Parken von Anrufen, z. B. wo Anrufe bei einem Zeit out umgeleitet werden und ob die Person auf dem Telefon beim Parken Musik hört. Sie können auch die Musikdatei angeben, die abspielt werden soll, während sich der Anruf in der Warteschleife befindet.
  
> [!NOTE]
> Angepasste Wartemusikdateien für das Parken von Anrufen werden nicht im Rahmen des Notfallwiederherstellungsprozesses von Skype for Business Server gesichert und gehen verloren, wenn die in den Pool hochgeladenen Dateien beschädigt, beschädigt oder gelöscht werden. Bewahren Sie immer eine separate Sicherungskopie der angepassten Wartemusikdateien auf, die Sie für das Parken von Anrufen hochgeladen haben. 
  
Die Anwendung zum Parken von Anrufen ist eine Komponente Enterprise-VoIP. Wenn Sie eine Enterprise-VoIP, wird die Anwendung zum Parken von Anrufen automatisch installiert und aktiviert. Bevor Sie das Parken von Anrufen verwenden können, muss der Enterprise-VoIP konfigurieren und für Benutzer über eine Sprachrichtlinie aktivieren.
  
## <a name="deployment-and-requirements"></a>Bereitstellung und Anforderungen

Die Anwendung zum Parken von Anrufen wird automatisch installiert, wenn Sie Enterprise-VoIP. Sie aktivieren das Parken von Anrufen, indem Sie eine Sprachrichtlinie konfigurieren.
  
### <a name="software-requirements"></a>Softwareanforderungen

Auf allen Front-End-Servern und Standard Edition-Servern, auf denen das Parken von Anrufen bereitgestellt wird, muss die Windows Media Format Runtime für Server mit Windows Server 2008 R2 oder Microsoft Media Foundation für Server mit Windows Server 2012 oder Windows Server 2012 R2 installiert sein. Für Windows Server 2008 R2 wird die Windows Media Format Runtime als Teil der Windows Desktop Experience installiert. Windows Media Format Runtime oder Microsoft Media Foundation ist für Windows Media Audio (.wma)-Dateien erforderlich, die das Parken von Anrufen für Wartemusik abspielen.
  
### <a name="port-requirements"></a>Portanforderungen

Die Anwendung zum Parken von Anrufen verwendet **Port 5075 für**  SIP-Abhöranforderungen.
    
> [!NOTE]
> Dieser Port ist die Standardeinstellung, die Sie mit dem Cmdlet **Set-CsApplicationServer** ändern können. Ausführliche Informationen zu diesem Cmdlet finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.
  
### <a name="audio-file-requirements"></a>Audiodateianforderungen

Die Anwendung zum Parken von Anrufen unterstützt nur Windows Media Audio (WMA)-Dateien für wartemusik. Sie können Dateien für Wartemusik mit Microsoft Expression Encoder 4 anpassen. Informationen zum Herunterladen von Expression Encoder 4 finden Sie [unter "Expression Encoder 4".](https://go.microsoft.com/fwlink/p/?linkId=202843) Verwenden Sie das Tool, um die Datei in ein WMA-Format zu konvertieren. Das empfohlene Format für Wartemusikdateien für die Anwendung zum Parken von Anrufen ist Media Audio 9, 44 kHz, 16 Bit, Mono, CBR oder 32 KBit/s.
  
> [!NOTE]
> Die konvertierte Datei wird über das Telefon nur mit 16 kHz abgespielt, auch wenn diese mit 44 kHz aufgezeichnet wurde. 
  
## <a name="supported-clients-and-calls"></a>Unterstützte Clients und Anrufe

Die folgenden Clients und Anruftypen werden für das Parken von Anrufen unterstützt.
  
### <a name="clients-supported-for-parking-calls"></a>Für das Parken von Anrufen unterstützte Clients

Anrufe von IP-, Nebenstellen-, Festnetz- oder Mobiltelefonen können geparkt werden.
  
> [!NOTE]
> Nur Audioanrufe können geparkt werden. Das Parken von Chatnachrichten und Konferenzen ist nicht möglich. 
  
Die folgenden Clients können das Parken von Anrufen verwenden, um Anrufe zu parken:
  
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
  
Die folgenden Clients können Anrufe abrufen, die beim Parken von Anrufen geparkt wurden:
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
- IP-Telefone in öffentlichen Bereichen
    
- Nicht-IP-Telefone, die mit der Skype for Business Server-Infrastruktur verbunden sind, einschließlich Telefonen in öffentlichen Bereich und Nebenstellentelefonen (Private Branch Exchange, PBX)
    
## <a name="call-park-capacity-planning"></a>Kapazitätsplanung für das Parken von Anrufen

In der folgenden Tabelle wird das Benutzermodell für das Parken von Anrufen beschrieben, das Sie als Grundlage für die Kapazitätsplanungsanforderungen verwenden können.
  
> [!IMPORTANT]
> Beachten Sie, dass bei der Kapazitätsplanung für die Notfallwiederherstellung jeder Pool eines Poolpaars in der Lage sein sollte, die Arbeitsauslastungen für Die Dienste zum Parken von Anrufen in beiden Pools zu verarbeiten. 
  
**Benutzermodell der Funktion zum Parken von Anrufen**

|**Metrik**|**Pro Front-End-Pool  <br/>  (mit 8 Front-End-Servern)**|**Pro Standard Edition-Server**|
|:-----|:-----|:-----|
|Rate für das Parken von Anrufen  <br/> |8 pro Minute  <br/> |1 pro Minute  <br/> |
|Rate für das Abrufen geparkter Anrufe  <br/> |8 pro Minute  <br/> |1 pro Minute  <br/> |
|Durchschnittliche Parkdauer  <br/> |60 Sekunden  <br/> |60 Sekunden  <br/> |
   

