---
title: Skype für die Business-Kompatibilität mit Office-apps
ms.author: jambirk
author: jambirk
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
ms.openlocfilehash: 186b8951718e6903ec7cc4f8c317504b74917716
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Skype für die Business-Kompatibilität mit Office-apps
 
Verstehen Sie, wie Sie Skype für Business-Features in Outlook und anderen Office-Anwendung zugreifen können.
  
In diesem Thema wird die Kompatibilität von Skype für Unternehmen mit verschiedenen Versionen von Microsoft Office-Suites. 
  
## <a name="office-and-skype-for-business"></a>Office und Skype für Unternehmen

Die folgende Tabelle beschreibt die Skype für Business-Features, die von den verschiedenen Versionen von Office unterstützt werden, nachdem Exchange bereitgestellt und gemäß [Integrieren Skype für Business Server 2015 mit Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)integriert ist.
  
**Skype für Unternehmen und Microsoft Office-Kompatibilität**

|**Funktion**|**Microsoft Office 2010**|**Microsoft Office 2013, 2015 und 2016**|**2016 von Office für Mac** & #x 2776; |
|:-----|:-----|:-----|:-----|
|**Outlook-features** <br/> ||||
|Outlook-Besprechungseinladungen anpassen (Logo, Hilfe-URL, Haftungsausschluss, Fußzeilentext hinzufügen)  <br/> |Nein  <br/> |Ja  <br/> |Nein  <br/> |
|Besprechungsoption konfigurieren, um Teilnehmeraudio und -video standardmäßig stummzuschalten  <br/> |Nein  <br/> |Ja  <br/> |Nein  <br/> |
|Einheitliche Kontaktspeicher für die Verwaltung von Kontaktlisten in Office und Skype für Unternehmen  <br/> |Nein  <br/> |Ja (erfordert Exchange 2013 oder höher)  <br/> |Ja  <br/> |
|Profilbilder mit hoher Auflösung  <br/> |Nein  <br/> |Ja (erfordert Exchange 2013 oder höher)  <br/> |Ja  <br/> |
|Anwesenheitsstatus in der Microsoft Outlook aus, an und Cc-Felder  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |
|Antworten mit Sofortnachricht oder einem Anruf aus dem Menü für Verfügbarkeit  <br/> |Ja (von der Visitenkarte aus)  <br/> |Ja (von der Visitenkarte aus)  <br/> |Ja (von der Visitenkarte aus)  <br/> |
|Anwesenheitsstatus in einer Besprechungsanfrage auf der Registerkarte „Terminplanungs-Assistent“  <br/> |Ja  <br/> |Ja  <br/> |Nein  <br/> |
|Antworten mit Sofortnachricht oder Anruf von der Symbolleiste oder dem Menüband in einer empfangenen e-Mail-Nachricht  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |
|**Weitere Office-apps** <br/> ||||
|Freigegebene OneNote-Notizen  <br/> |Nein  <br/> |Ja  <br/> |Nein  <br/> |
|Integration des Setups in das Office-Setupprogramm  <br/> |Nein  <br/> |Ja  <br/> |Nein  <br/> |
|PowerPoint-Präsentationsinhalt  <br/> |Ja  <br/> |Ja  <br/> (VBSS ebenfalls verfügbar)  <br/> |Ja  <br/> |
|Chat und Anwesenheitsinformationen in Microsoft Word- und Microsoft Excel-Dateien (Smarttags aktiviert)  <br/> |Nur Microsoft Word  <br/> |Nur Microsoft Word  <br/> |Nein  <br/> |
|Chat und Anwesenheitsinformationen in Microsoft SharePoint-Websites (Outlook muss installiert sein.)  <br/> |Ja  <br/> |Ja  <br/> |Nein  <br/> |
   
& #x 2776; – Setzt voraus installiert haben und derzeit einen Skype für Unternehmen auf Mac-Client oder die Lync 2011 für Mac-Client ausgeführt werden.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server und Skype für Unternehmen

Die folgende Tabelle beschreibt die Skype für die Business-Unterstützung für die verschiedenen Versionen von Exchange Server. Outlook muss installiert sein, auf dem Clientcomputer um Extended MAPI-Aufrufe zu verarbeiten, und einige Features erfordern die Verwendung des Exchange-Webdienste (EWS).
  
**Skype für Unternehmen und Exchange Server-Kompatibilität**

|**Exchange Server-version**|**Skype für die Business-Unterstützung**|
|:-----|:-----|
|Exchange Server 2016  <br/> |Identisch mit der Exchange Server 2013-Unterstützung  <br/> |
|Exchange Server 2013  <br/> |Identisch mit Exchange Server 2010 unterstützt, durch die hinzugefügte  <br/>&bull;&nbsp;&nbsp;Einheitlicher Kontaktspeicher  <br/>&bull;&nbsp;&nbsp;Bilder mit hoher Auflösung  <br/>&bull;&nbsp;&nbsp;Integration der Archivierung  <br/> **Hinweis:** Weitere Informationen hierzu finden Sie unter [Skype für Business Server 2015 mit Exchange Server zu integrieren](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Exchange Server 2010  <br/> |Die folgenden Funktionen stehen nur über EWS zur Verfügung:  <br/>&bull;&nbsp;&nbsp;Lesen oder Löschen von Elementen im Ordner "Unterhaltungsverlauf"  <br/>&bull;&nbsp;&nbsp;Lesen oder Löschen von voicemailelementen  <br/>&bull;&nbsp;&nbsp;Anzeigen erweiterter Frei-/Gebucht-Informationen und Besprechungsbetreff und-Ort  <br/>&bull;&nbsp;&nbsp;Exchange-kontaktsynchronisierung  <br/> Öffentliche Ordner sind in Exchange Server 2010 optional.  <br/> |
   
## <a name="see-also"></a>Siehe auch
 

[Clientanforderungen für Windows und Software-support](windows-requirements.md)
  
[Planen von Besprechungen-Clients (Web App und Besprechungen App)](meetings-clients.md)
#### 

[Clientinteroperabilität in Lync 2013](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)
  
[Clientsystemanforderungen](http://technet.microsoft.com/library/38f3a465-dac1-4381-bc59-270a4ef07ced.aspx)
  
[Lync Windows Store-App-Anforderungen](http://technet.microsoft.com/library/5f2e0a40-8450-4f61-b6f6-913fc1906020.aspx)

