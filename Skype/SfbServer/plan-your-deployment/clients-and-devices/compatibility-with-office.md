---
title: Skype for Business-Kompatibilität mit Office-Apps
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: Grundlegendes zu den Möglichkeiten, wie Sie in Outlook und anderen Microsoft Office-Anwendungen auf Skype for Business-Funktionen zugreifen können.
ms.openlocfilehash: c24c6b08e21db357d52b1cc130e53f23b6123ff6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277433"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Skype for Business-Kompatibilität mit Office-Apps
 
Grundlegendes zu den Möglichkeiten, wie Sie in Outlook und anderen Microsoft Office-Anwendungen auf Skype for Business-Funktionen zugreifen können.
  
In diesem Thema wird die Kompatibilität von Skype for Business mit verschiedenen Versionen von Microsoft Office-Suites beschrieben. 
  
## <a name="office-and-skype-for-business"></a>Office und Skype for Business

In der folgenden Tabelle werden die Skype for Business-Features beschrieben, die von verschiedenen Office-Versionen unterstützt werden, sobald Exchange bereitgestellt und integriert ist, wie unter [integrieren von Skype for Business Server mit Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)beschrieben.
  
**Kompatibilität von Skype for Business und Microsoft Office**

|**Funktion**|**Microsoft Office 2010**|**Microsoft Office 2013, 2015 und 2016**|**Office 2016 für Mac** & # x2776; |
|:-----|:-----|:-----|:-----|
|**Outlook-Funktionen** ||||
|Outlook-Besprechungseinladungen anpassen (Logo, Hilfe-URL, Haftungsausschluss, Fußzeilentext hinzufügen)  |Nein  |Ja    |Ja|
|Besprechungsoption konfigurieren, um Teilnehmeraudio und -video standardmäßig stummzuschalten    |Nein    |Ja    |Nein    |
|Einheitlicher Kontaktspeicher zum Verwalten von Kontaktlisten in Office und Skype for Business    |Nein    |Ja (erfordert Exchange 2013 oder höher)    |Ja    |
|Profil Bilder mit hoher Auflösung    |Nein    |Ja (erfordert Exchange 2013 oder höher)    |Ja    |
|Anwesenheitsstatus in den Feldern "Microsoft Outlook von", "an" und "CC"    |Ja     |Ja     |Ja    |
|Mit Chat oder Anruf über das Verfügbarkeits Menü Antworten    |Ja (von der Visitenkarte aus)    |Ja (von der Visitenkarte aus)    |Ja (von der Visitenkarte aus)    |
|Anwesenheitsstatus in einer Besprechungsanfrage auf der Registerkarte „Terminplanungs-Assistent“    |Ja     |Ja    |Nein    |
|Antworten mit Chatnachrichten oder anrufen über die Symbolleiste oder das Menüband in einer empfangenen e-Mail-Nachricht    |Ja     |Ja     |Ja    |
|**Andere Office-Apps**   ||||
|Freigegebene OneNote-Notizen    |Nein    |Ja    |Nein    |
|Integration des Setups in das Office-Setupprogramm    |Nein    |Ja    |Nein    |
|PowerPoint-Präsentationsinhalt    |Ja    |Ja (schlechte VBSS auch verfügbar)    |Ja    |
|Chat und Anwesenheitsinformationen in Microsoft Word- und Microsoft Excel-Dateien (Smarttags aktiviert)    |Nur Microsoft Word    |Nur Microsoft Word    |Nein    |
|Chat und Anwesenheitsinformationen in Microsoft SharePoint-Websites (Outlook muss installiert sein.)    |Ja    |Ja    |Nein    |
   
&#x2776; -Geht davon aus, dass Sie einen Skype for Business für Mac-Client oder den lync 2011 für Mac-Client installiert haben und derzeit ausgeführt werden.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server und Skype for Business

In der folgenden Tabelle wird der Skype for Business-Support für verschiedene Versionen von Exchange Server beschrieben. Outlook muss auf dem Clientcomputer installiert sein, um erweiterte MAPI-Aufrufe behandeln zu können, und einige Features erfordern die Verwendung von Exchange-Webdiensten (EWS).
  
**Skype for Business und Exchange Server-Kompatibilität**

|**Exchange Server-Version**|**Skype for Business-Support**|
|:-----|:-----|
|Exchange Server 2019 (nur Skype for Business Server 2019) |Identisch mit der Exchange Server 2013-Unterstützung    |
|Exchange Server 2016    |Identisch mit der Exchange Server 2013-Unterstützung  <br/> |
|Exchange Server 2013  <br/> |Identisch mit Exchange Server 2010-Unterstützung mit dem Zusatz von  <br/>&bull;&nbsp;&nbsp;Einheitlicher Kontaktspeicher  <br/>&bull;&nbsp;&nbsp;Bilder mit hoher Auflösung  <br/>&bull;&nbsp;&nbsp;Archivierungs Integration  <br/> **Hinweis:** Ausführliche Informationen finden Sie unter [integrieren von Skype for Business Server mit Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Exchange Server 2010  <br/>(Nur Skype for Business Server 2015) |Die folgenden Funktionen stehen nur über EWS zur Verfügung:  <br/>&bull;&nbsp;&nbsp;Lesen oder Löschen von Elementen im Ordner "Konversationsprotokoll"  <br/>&bull;&nbsp;&nbsp;Lesen oder Löschen von Voicemail-Elementen  <br/>&bull;&nbsp;&nbsp;Anzeigen von erweiterten Frei/Gebucht-Informationen sowie Betreff und Ort der Besprechung  <br/>&bull;&nbsp;&nbsp;Exchange-Kontaktsynchronisierung  <br/> Öffentliche Ordner sind in Exchange Server 2010 optional.  <br/> |
   
## <a name="see-also"></a>Siehe auch
 
[Windows-Clientanforderungen und Software Support](windows-requirements.md)
  
[Planen von Besprechungs Clients (app für Web App und Besprechungen)](meetings-clients.md)

