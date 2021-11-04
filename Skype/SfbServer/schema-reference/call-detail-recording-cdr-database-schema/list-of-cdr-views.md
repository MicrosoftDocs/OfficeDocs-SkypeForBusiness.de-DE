---
title: Liste von KDS-Ansichten
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
description: Ansichten bieten eine einfache Möglichkeit, auf Informationen zu den gängigsten Szenarien zuzugreifen, die zum Zurückgeben von Daten aus der KDS-Datenbank verwendet werden. Es wird empfohlen, Ansichten zum Erstellen von benutzerdefinierten Berichten zu verwenden, anstatt die tatsächlichen KDS-Datenbanktabellen zu verwenden. Dies liegt daran, dass die Datenbankansichten mit größerer Wahrscheinlichkeit die Abwärtskompatibilität mit zukünftigen Versionen aufrechterhalten.
ms.openlocfilehash: 7154319dba584516dcff3c41d23e5af31bee4621
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746611"
---
# <a name="list-of-cdr-views"></a>Liste von KDS-Ansichten
 
Ansichten bieten eine einfache Möglichkeit, auf Informationen zu den gängigsten Szenarien zuzugreifen, die zum Zurückgeben von Daten aus der KDS-Datenbank verwendet werden. Es wird empfohlen, Ansichten zum Erstellen von benutzerdefinierten Berichten zu verwenden, anstatt die tatsächlichen KDS-Datenbanktabellen zu verwenden. Dies liegt daran, dass die Datenbankansichten mit größerer Wahrscheinlichkeit die Abwärtskompatibilität mit zukünftigen Versionen aufrechterhalten.
  
|**Sichtname**|**Beschreibung**|
|:-----|:-----|
|[ClientVersions-Ansicht](clientversions-0.md) <br/> |Gibt Informationen zu den in einer Kommunikationssitzung verwendeten Clientsoftwareanwendungen/Geräten zurück.  <br/> |
|[ConferenceMessageCount-Ansicht](conferencemessagecount-0.md) <br/> |Gibt Informationen zu der Anzahl der von Benutzern in einer Konferenz gesendeten Nachrichten zurück.  <br/> |
|[Konferenzansicht](conferences-0.md) <br/> |Gibt Konferenzinformationen zurück, einschließlich Startzeit, Endzeit und Konferenzorganisator.  <br/> |
|[ConferenceSessionDetails-Ansicht](conferencesessiondetails.md) <br/> |Gibt Sitzungsdetails zu allen Konferenzsitzungen zurück, einschließlich Start- und Endzeit, Benutzer-IDs, Antwortcodes und Diagnose-IDs.  <br/> |
|[ConferenceUris-Ansicht](conferenceuris-0.md) <br/> |Gibt Informationen zu den in einer Konferenz verwendeten Konferenz-URIs zurück.  <br/> |
|[ErrorReport-Ansicht](errorreport-0.md) <br/> |Gibt Informationen zu Fehlern zurück, die in einer Sitzung aufgetreten sind.  <br/> |
|[FileTransfers-Ansicht](filetransfers.md) <br/> |Gibt Informationen zu Dateiübertragungssitzungen zurück. Hierzu gehören der Dateiname und Angaben dazu, ob die Übertragung akzeptiert, abgelehnt oder abgebrochen wurde.  <br/> |
|[FocusJoinsAndLeaves-Ansicht](focusjoinsandleaves-0.md) <br/> |Gibt Informationen zu Aktivitäten zum Beitreten oder Verlassen einer Konferenz zurück.  <br/> |
|[McuJoinsAndLeaves-Ansicht](mcujoinsandleaves-0.md) <br/> |Gibt kombinierte Informationen zu Aktivitäten zum Beitreten oder Verlassen einer Konferenz zurück (jeder Konferenzbeitritt ist entsprechend mit dem Verlassen einer Konferenz gepaart).  <br/> |
|[Mcus-Ansicht](mcus-0.md) <br/> |Gibt Informationen zu Konferenzservern zurück.  <br/> |
|[Medienansicht](media-0.md) <br/> |Gibt Informationen zu den Medientypen zurück, die in Peer-zu-Peer-Kommunikationssitzungen verwendet werden.  <br/> |
|[ProgressReport-Ansicht](progressreport-0.md) <br/> |Gibt Informationen zu beendeten Konferenzsitzungen zurück.  <br/> |
|[Registrierungsansicht](registration-0.md) <br/> |Gibt Informationen zu Registrierungen mit Skype for Business Server 2015 zurück.  <br/> |
|[SessionDetails-Ansicht](sessiondetails-0.md) <br/> |Gibt Informationen zu Peer-zu-Peer-Sitzungen zurück, einschließlich Telefonanrufen von VoIP zu VoIP, Chatsitzungen mit zwei Teilnehmern oder anderen Peer-zu-Peer-Kommunikationssitzungen.  <br/> |
|[Benutzeransicht](user.md) <br/> |Gibt Informationen zu den Benutzern zurück, die an Kommunikationssitzungen teilgenommen haben.  <br/> |
|[VoIPDetails-Ansicht](voipdetails.md) <br/> |Gibt Informationen zu Peer-to-Peer-Sitzungen zurück, an denen mindestens ein VoIP-Benutzer beteiligt war.  <br/> |
   

