---
title: Skype for Business Kompatibilität mit Office Apps
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: Erfahren Sie, wie Sie über Outlook und andere Microsoft Office-Anwendungen auf Skype for Business Features zugreifen können.
ms.openlocfilehash: b1a2aad241d0da2ef253d27b1b83bf9b1140fa79745b924cd0e4438660e4d3e0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54297141"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Skype for Business Kompatibilität mit Office Apps
 
Erfahren Sie, wie Sie über Outlook und andere Microsoft Office-Anwendungen auf Skype for Business Features zugreifen können.
  
In diesem Thema wird die Kompatibilität von Skype for Business mit verschiedenen Versionen von Microsoft Office Suites beschrieben. 
  
## <a name="office-and-skype-for-business"></a>Office und Skype for Business

In der folgenden Tabelle werden die Skype for Business Features beschrieben, die von verschiedenen Versionen von Office unterstützt werden, sobald Exchange bereitgestellt und integriert wurde, wie in ["Integrieren Skype for Business Server in Exchange Server"](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)beschrieben.
  
**Skype for Business- und Microsoft Office kompatibilität**

|**Feature**|**Microsoft Office 2010**|**Microsoft Office 2013, 2015 und 2016**|**Office 2016 für Mac** &#x2776; |
|:-----|:-----|:-----|:-----|
|**Outlook Features** ||||
|Anpassen Outlook Besprechungseinladungen (Logo hinzufügen, Hilfe-URL, Haftungsausschluss, Fußzeilentext)  |Nein  |Ja   |Ja|
|Konfigurieren der Besprechungsoption zum standardmäßigen Stummschalten von Audio- und Videoinhalten für Teilnehmer    |Nein    |Ja    |Nein    |
|Einheitliche Kontakt-Store zum Verwalten von Kontaktlisten über Office und Skype for Business    |Nein    |Ja (erfordert Exchange 2013 oder höher)    |Ja    |
|Hochauflösende Profilbilder    |Nein    |Ja (erfordert Exchange 2013 oder höher)    |Ja    |
|Anwesenheitsstatus in den Feldern "Microsoft Outlook Von", "An" und "Cc"    |Ja    |Ja    |Ja    |
|Antworten mit Chat oder Anruf über das Verfügbarkeitsmenü    |Ja (von der Visitenkarte aus)    |Ja (von der Visitenkarte aus)    |Ja (von der Visitenkarte aus)    |
|Anwesenheitsstatus in einer Besprechungsanfrage auf der Registerkarte Terminplanungs-Assistent    |Ja    |Ja    |Nein    |
|Antworten mit Chat oder Anruf von der Symbolleiste oder dem Menüband in einer empfangenen E-Mail-Nachricht    |Ja    |Ja    |Ja    |
|**Andere Office-Apps**   ||||
|OneNote freigegebene Notizen    |Nein    |Ja    |Nein    |
|Setup, das in das Office Setupprogramm integriert ist    |Nein    |Ja    |Nein    |
|PowerPoint Präsentationsinhalt    |Ja    |Ja (VBSS auch verfügbar)    |Ja    |
|Sofortnachrichten und Anwesenheitsinformationen in Microsoft Word- und Microsoft Excel-Dateien (Smarttags aktiviert)    |Nur Microsoft Word    |Nur Microsoft Word    |Nein    |
|Sofortnachrichten und Anwesenheitsinformationen in Microsoft SharePoint-Websites (Outlook muss installiert sein)    |Ja    |Ja    |Nein    |
   
&#x2776; : Geht davon aus, dass Sie einen Skype for Business auf dem Mac-Client oder dem Lync 2011 für Mac-Client installiert haben und derzeit ausführen.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server und Skype for Business

In der folgenden Tabelle wird Skype for Business Unterstützung für verschiedene Versionen von Exchange Server beschrieben. Outlook müssen auf dem Clientcomputer installiert sein, um erweiterte MAPI-Aufrufe verarbeiten zu können, und einige Features erfordern die Verwendung von Exchange Webdienste (EWS).
  
**Skype for Business- und Exchange Server kompatibilität**

|**Exchange Server-Version**|**Skype for Business-Unterstützung**|
|:-----|:-----|
|Exchange Server 2019 (nur Skype for Business Server 2019) |Identisch mit Exchange Server 2013-Unterstützung    |
|Exchange Server 2016    |Identisch mit Exchange Server 2013-Unterstützung  <br/> |
|Exchange Server 2013  <br/> |Identisch mit Exchange Server 2010-Unterstützung, mit dem Hinzufügen von  <br/>&bull;&nbsp;&nbsp;Einheitliche Kontakt-Store  <br/>&bull;&nbsp;&nbsp;Bilder mit hoher Auflösung  <br/>&bull;&nbsp;&nbsp;Archivierungsintegration  <br/> **Hinweis:** Ausführliche Informationen finden Sie unter [Integrieren von Skype for Business Server in Exchange Server.](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)  <br/> |
|Exchange Server 2010  <br/>(nur Skype for Business Server 2015) |Die folgenden Funktionen stehen nur über die EWS zur Verfügung:  <br/>&bull;&nbsp;&nbsp;Lesen oder Löschen von Elementen im Ordner "Aufgezeichnete Unterhaltungen"  <br/>&bull;&nbsp;&nbsp;Lesen oder Löschen von Voicemailelementen  <br/>&bull;&nbsp;&nbsp;Anzeigen erweiterter Frei/Gebucht-Informationen sowie des Besprechungsthemas und -orts  <br/>&bull;&nbsp;&nbsp;Exchange Kontaktsynchronisierung  <br/> Öffentliche Ordner sind in Exchange Server 2010 optional.  <br/> |
   
## <a name="see-also"></a>Siehe auch
 
[Windows Clientanforderungen und Softwareunterstützung](windows-requirements.md)
  
[Planen von Besprechungsclients (Web App und Besprechungs-App)](meetings-clients.md)

