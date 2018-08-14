---
title: Skype für die Business-Kompatibilität mit Office-apps
ms.author: jambirk
author: PhillipGarding
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: Verstehen Sie, wie Sie Skype für Business-Features in Outlook und anderen Office-Anwendung zugreifen können.
ms.openlocfilehash: 22319a814ac1f09e67143f71a705c44b1e820e0e
ms.sourcegitcommit: 47f80b977fa7de3b83a521164f765623bffcf5c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2018
ms.locfileid: "22391840"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Skype für die Business-Kompatibilität mit Office-apps
 
Verstehen Sie, wie Sie Skype für Business-Features in Outlook und anderen Office-Anwendung zugreifen können.
  
In diesem Thema wird die Kompatibilität von Skype für Unternehmen mit verschiedenen Versionen von Microsoft Office-Suites. 
  
## <a name="office-and-skype-for-business"></a>Office und Skype für Unternehmen

Die folgende Tabelle beschreibt die Skype für Business-Features, die von den verschiedenen Versionen von Office unterstützt werden, nachdem Exchange bereitgestellt und gemäß [Integrieren Skype für Business Server mit Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)integriert ist.
  
**Skype für Unternehmen und Microsoft Office-Kompatibilität**

|**Funktion**|**Microsoft Office 2010**|**Microsoft Office 2013, 2015 und 2016**|**2016 von Office für Mac** & #x 2776; |
|:-----|:-----|:-----|:-----|
|**Outlook-Funktionen** ||||
|Outlook-Besprechungseinladungen anpassen (Logo, Hilfe-URL, Haftungsausschluss, Fußzeilentext hinzufügen)  |Nein  |Ja   |Ja|
|Besprechungsoption konfigurieren, um Teilnehmeraudio und -video standardmäßig stummzuschalten    |Nein    |Ja    |Nein    |
|Einheitliche Kontaktspeicher für die Verwaltung von Kontaktlisten in Office und Skype für Unternehmen    |Nein    |Ja (erfordert Exchange 2013 oder höher)    |Ja    |
|Profilbilder mit hoher Auflösung    |Nein    |Ja (erfordert Exchange 2013 oder höher)    |Ja    |
|Anwesenheitsstatus in der Microsoft Outlook aus, an und Cc-Felder    |Ja    |Ja    |Ja    |
|Antworten mit Sofortnachricht oder einem Anruf aus dem Menü für Verfügbarkeit    |Ja (von der Visitenkarte aus)    |Ja (von der Visitenkarte aus)    |Ja (von der Visitenkarte aus)    |
|Anwesenheitsstatus in einer Besprechungsanfrage auf der Registerkarte „Terminplanungs-Assistent“    |Ja    |Ja    |Nein    |
|Antworten mit Sofortnachricht oder Anruf von der Symbolleiste oder dem Menüband in einer empfangenen e-Mail-Nachricht    |Ja    |Ja    |Ja    |
|**Weitere Office-apps**   ||||
|Freigegebene OneNote-Notizen    |Nein    |Ja    |Nein    |
|Integration des Setups in das Office-Setupprogramm    |Nein    |Ja    |Nein    |
|PowerPoint-Präsentationsinhalt    |Ja    |Ja (VBSS auch verfügbar)    |Ja    |
|Chat und Anwesenheitsinformationen in Microsoft Word- und Microsoft Excel-Dateien (Smarttags aktiviert)    |Nur Microsoft Word    |Nur Microsoft Word    |Nein    |
|Chat und Anwesenheitsinformationen in Microsoft SharePoint-Websites (Outlook muss installiert sein.)    |Ja    |Ja    |Nein    |
   
& #x 2776; – Setzt voraus installiert haben und derzeit einen Skype für Unternehmen auf Mac-Client oder die Lync 2011 für Mac-Client ausgeführt werden.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server und Skype für Unternehmen

Die folgende Tabelle beschreibt die Skype für die Business-Unterstützung für die verschiedenen Versionen von Exchange Server. Outlook muss installiert sein, auf dem Clientcomputer um Extended MAPI-Aufrufe zu verarbeiten, und einige Features erfordern die Verwendung des Exchange-Webdienste (EWS).
  
**Skype für Unternehmen und Exchange Server-Kompatibilität**

|**Exchange Server-Version**|**Skype für die Business-Unterstützung**|
|:-----|:-----|
|Exchange Server 2019 (Skype für Business Server 2019 nur) |Identisch mit der Exchange Server 2013-Unterstützung    |
|Exchange Server 2016    |Identisch mit der Exchange Server 2013-Unterstützung  <br/> |
|Exchange Server 2013  <br/> |Identisch mit Exchange Server 2010 unterstützt, durch die hinzugefügte  <br/>&bull;&nbsp;&nbsp;Einheitlicher Kontaktspeicher  <br/>&bull;&nbsp;&nbsp;Bilder mit hoher Auflösung  <br/>&bull;&nbsp;&nbsp;Integration der Archivierung  <br/> **Hinweis:** Weitere Informationen hierzu finden Sie unter [Skype für Business Server mit Exchange Server zu integrieren](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Exchange Server 2010  <br/>(Skype für Business Server 2015 nur) |Die folgenden Funktionen stehen nur über EWS zur Verfügung:  <br/>&bull;&nbsp;&nbsp;Lesen oder Löschen von Elementen im Ordner "Unterhaltungsverlauf"  <br/>&bull;&nbsp;&nbsp;Lesen oder Löschen von voicemailelementen  <br/>&bull;&nbsp;&nbsp;Anzeigen erweiterter Frei-/Gebucht-Informationen und Besprechungsbetreff und-Ort  <br/>&bull;&nbsp;&nbsp;Exchange-kontaktsynchronisierung  <br/> Öffentliche Ordner sind in Exchange Server 2010 optional.  <br/> |
   
## <a name="see-also"></a>Siehe auch
 
[Clientanforderungen für Windows und Software-support](windows-requirements.md)
  
[Planen von Besprechungen-Clients (Web App und Besprechungen App)](meetings-clients.md)

