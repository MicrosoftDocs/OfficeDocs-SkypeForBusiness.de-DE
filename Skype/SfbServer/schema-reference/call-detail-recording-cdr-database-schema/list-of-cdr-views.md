---
title: Liste von KDS-Ansichten
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
description: 'Ansichten bieten eine einfache Möglichkeit zum Zugreifen auf Informationen zu den am häufigsten verwendeten Szenarien für die Rückgabe von Daten aus der CDR-Datenbank. Es wird empfohlen, ansichten zum Erstellen benutzerdefinierter Berichte zu verwenden, anstatt die tatsächlichen Tabellen der #A0 zu verwenden. Dies liegt daran, dass die Datenbankansichten mit der wahrscheinlicheren Abwärtskompatibilität mit zukünftigen Versionen kompatibel sind.'
ms.openlocfilehash: 0a3b40c9b31bb521075e78a1a8d46479200249d5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813155"
---
# <a name="list-of-cdr-views"></a>Liste von KDS-Ansichten
 
Ansichten bieten eine einfache Möglichkeit zum Zugreifen auf Informationen zu den am häufigsten verwendeten Szenarien für die Rückgabe von Daten aus der CDR-Datenbank. Es wird empfohlen, ansichten zum Erstellen benutzerdefinierter Berichte zu verwenden, anstatt die tatsächlichen Tabellen der #A0 zu verwenden. Dies liegt daran, dass die Datenbankansichten mit der wahrscheinlicheren Abwärtskompatibilität mit zukünftigen Versionen kompatibel sind.
  
|**Sichtname**|**Beschreibung**|
|:-----|:-----|
|[Ansicht "ClientVersions"](clientversions-0.md) <br/> |Gibt Informationen zu den in einer Kommunikationssitzung verwendeten Clientsoftwareanwendungen/Geräten zurück.  <br/> |
|[Ansicht "ConferenceMessageCount"](conferencemessagecount-0.md) <br/> |Gibt Informationen zu der Anzahl der von Benutzern in einer Konferenz gesendeten Nachrichten zurück.  <br/> |
|[Ansicht "Konferenzen"](conferences-0.md) <br/> |Gibt Konferenzinformationen zurück, einschließlich Startzeit, Endzeit und Konferenzorganisator.  <br/> |
|[#A0](conferencesessiondetails.md) <br/> |Gibt Sitzungsdetails zu allen Konferenzsitzungen zurück, einschließlich Start- und Endzeit, Benutzer-IDs, Antwortcodes und Diagnose-IDs.  <br/> |
|[Ansicht "ConferenceUris"](conferenceuris-0.md) <br/> |Gibt Informationen zu den in einer Konferenz verwendeten Konferenz-URIs zurück.  <br/> |
|[Ansicht "ErrorReport"](errorreport-0.md) <br/> |Gibt Informationen zu Fehlern zurück, die in einer Sitzung aufgetreten sind.  <br/> |
|[Ansicht "FileTransfers"](filetransfers.md) <br/> |Gibt Informationen zu Dateiübertragungssitzungen zurück. Hierzu gehören der Dateiname und Angaben dazu, ob die Übertragung akzeptiert, abgelehnt oder abgebrochen wurde.  <br/> |
|[Ansicht "FocusJoinsAndLeaves"](focusjoinsandleaves-0.md) <br/> |Gibt Informationen zu Aktivitäten zum Beitreten oder Verlassen einer Konferenz zurück.  <br/> |
|[Ansicht "McuJoinsAndLeaves"](mcujoinsandleaves-0.md) <br/> |Gibt kombinierte Informationen zu Aktivitäten zum Beitreten oder Verlassen einer Konferenz zurück (jeder Konferenzbeitritt ist entsprechend mit dem Verlassen einer Konferenz gepaart).  <br/> |
|[Ansicht "Mcus"](mcus-0.md) <br/> |Gibt Informationen zu Konferenzservern zurück.  <br/> |
|[Medienansicht](media-0.md) <br/> |Gibt Informationen zu den Medientypen zurück, die in Peer-zu-Peer-Kommunikationssitzungen verwendet werden.  <br/> |
|[Statusberichtsansicht](progressreport-0.md) <br/> |Gibt Informationen zu beendeten Konferenzsitzungen zurück.  <br/> |
|[Registrierungsansicht](registration-0.md) <br/> |Gibt Informationen zu Registrierungen bei Skype for Business Server 2015 zurück.  <br/> |
|[#A0](sessiondetails-0.md) <br/> |Gibt Informationen zu Peer-zu-Peer-Sitzungen zurück, einschließlich Telefonanrufen von VoIP zu VoIP, Chatsitzungen mit zwei Teilnehmern oder anderen Peer-zu-Peer-Kommunikationssitzungen.  <br/> |
|[Benutzeransicht](user.md) <br/> |Gibt Informationen zu den Benutzern zurück, die an Kommunikationssitzungen teilgenommen haben.  <br/> |
|[#A0](voipdetails.md) <br/> |Gibt Informationen zu Peer-to-Peer-Sitzungen zurück, an denen mindestens ein VoIP-Benutzer beteiligt war.  <br/> |
   

