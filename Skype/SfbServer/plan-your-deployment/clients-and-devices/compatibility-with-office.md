---
title: Kompatibilität von Skype for Business mit Office-Apps
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
description: Machen Sie sich mit den Möglichkeiten des Zugriffs auf Skype for Business-Features von Outlook und anderen Microsoft Office aus.
ms.openlocfilehash: b3d792d5e6376e4d845aa74f0585acf7d9a70d81
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802735"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Kompatibilität von Skype for Business mit Office-Apps
 
Verstehen Sie, wie Sie von Outlook und anderen Anwendungen aus auf Skype for Business-Features Microsoft Office können.
  
In diesem Thema wird die Kompatibilität von Skype for Business mit verschiedenen Versionen von Microsoft Office beschrieben. 
  
## <a name="office-and-skype-for-business"></a>Office und Skype for Business

In der folgenden Tabelle werden die Skype for Business-Features beschrieben, die von verschiedenen Versionen von Office unterstützt werden, sobald Exchange bereitgestellt und integriert ist, wie in "Integrieren von Skype for Business Server in [Exchange Server" beschrieben.](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
**Skype for Business und Microsoft Office A0**

|**Funktion**|**Microsoft Office 2010**|**Microsoft Office 2013, 2015 und 2016**|**Office 2016 für Mac** &#x2776; |
|:-----|:-----|:-----|:-----|
|**Features von Outlook** ||||
|Anpassen von Outlook-Besprechungseinladungen (Logo hinzufügen, Hilfe-URL, Haftungsausschluss, Fußzeilentext)  |Nein  |Ja   |Ja|
|Konfigurieren der Besprechungsoption zum standardmäßigen Stummschalten von Audio- und Videodaten von Teilnehmern    |Nein    |Ja    |Nein    |
|Einheitlicher Kontaktspeicher für die Verwaltung von Kontaktlisten in Office und Skype for Business    |Nein    |Ja (erfordert Exchange 2013 oder höher)    |Ja    |
|Hochauflösende Profilbilder    |Nein    |Ja (erfordert Exchange 2013 oder höher)    |Ja    |
|Anwesenheitsstatus in den Feldern "Von", "An" und "Cc" in Microsoft Outlook    |Ja    |Ja    |Ja    |
|Antworten mit Dem Anruf oder dem Anruf über das Verfügbarkeitsmenü    |Ja (von der Visitenkarte aus)    |Ja (von der Visitenkarte aus)    |Ja (von der Visitenkarte aus)    |
|Anwesenheitsstatus in einer Besprechungsanfrage auf der Registerkarte Terminplanungs-Assistent    |Ja    |Ja    |Nein    |
|Antworten mit Einer Nachricht oder einem Anruf über die Symbolleiste oder das Menüband in einer empfangenen E-Mail-Nachricht    |Ja    |Ja    |Ja    |
|**Andere Office-Apps**   ||||
|Freigegebene Notizen in OneNote    |Nein    |Ja    |Nein    |
|In das Office-Setup-Programm integriertes Setup    |Nein    |Ja    |Nein    |
|Inhalt der PowerPoint-Präsentation    |Ja    |Ja (VBSS auch verfügbar)    |Ja    |
|Sofortnachrichten und Anwesenheitsinformationen in Microsoft Word- und Microsoft Excel-Dateien (Smarttags aktiviert)    |Nur Microsoft Word    |Nur Microsoft Word    |Nein    |
|Sofortnachrichten und Anwesenheitsinformationen in Microsoft SharePoint-Websites (Outlook muss installiert sein)    |Ja    |Ja    |Nein    |
   
&#x2776; : Es wird davon ausgegangen, dass Sie einen Skype for Business auf einem Mac-Client oder den Lync 2011 für Mac-Client installiert haben und derzeit ausführen.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server und Skype for Business

In der folgenden Tabelle wird die Skype for Business-Unterstützung für verschiedene Versionen von Exchange Server. Outlook muss auf dem Clientcomputer installiert sein, um erweiterte MAPI-Aufrufe verarbeiten zu können, und einige Features erfordern die Verwendung von Exchange Web Services (EWS).
  
**Skype for Business und Exchange Server A0**

|**Exchange Server-Version**|**Skype for Business Support**|
|:-----|:-----|
|Exchange Server 2019 (nur Skype for Business Server 2019) |Identisch mit Exchange Server 2013-Unterstützung    |
|Exchange Server 2016    |Identisch mit Exchange Server 2013-Unterstützung  <br/> |
|Exchange Server 2013  <br/> |Identisch mit Exchange Server 2010-Support, zusätzlich  <br/>&bull;&nbsp;&nbsp;Einheitlicher Kontaktspeicher  <br/>&bull;&nbsp;&nbsp;Hochauflösende Bilder  <br/>&bull;&nbsp;&nbsp;Archivierungsintegration  <br/> **Hinweis:** Weitere Informationen finden Sie unter [Integrieren von Skype for Business Server in Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Exchange Server 2010  <br/>(nur Skype for Business Server 2015) |Die folgenden Funktionen stehen nur über die EWS zur Verfügung:  <br/>&bull;&nbsp;&nbsp;Lesen oder Löschen von Elementen im Ordner "Unterhaltungsverlauf"  <br/>&bull;&nbsp;&nbsp;Lesen oder Löschen von Voicemailelementen  <br/>&bull;&nbsp;&nbsp;Anzeigen erweiterter Frei/Gebucht-Informationen sowie des Betreffs und Orts der Besprechung  <br/>&bull;&nbsp;&nbsp;Synchronisierung von Exchange-Kontakten  <br/> Öffentliche Ordner sind in Exchange Server 2010 optional.  <br/> |
   
## <a name="see-also"></a>Siehe auch
 
[Anforderungen und Softwareunterstützung für den Windows-Client](windows-requirements.md)
  
[Planen von Besprechungsclients (Web App und Besprechungs-App)](meetings-clients.md)

