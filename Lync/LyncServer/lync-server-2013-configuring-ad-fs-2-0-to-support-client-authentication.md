---
title: 'Lync Server 2013: Konfigurieren von AD FS 2.0 zur Unterstützung der Clientauthentifizierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring AD FS 2.0 to support client authentication
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308565(v=OCS.15)
ms:contentKeyID: 54973687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7054bae609b5d1a1c6fe176c1092614f5d30fa6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a>Konfigurieren AD FS 2.0 zur Unterstützung der Clientauthentifizierung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-07-03_

Es gibt zwei mögliche Authentifizierungstypen, die so konfiguriert werden können, dass AD FS 2.0 die Authentifizierung mithilfe von Smartcards unterstützt:

  - Formularbasierte Authentifizierung (FBA)

  - Transport Layer Security-Client Authentifizierung

Mithilfe der formularbasierten Authentifizierung können Sie eine Webseite entwickeln, die es Benutzern ermöglicht, sich entweder mithilfe Ihres Benutzernamens/Kennworts oder mithilfe Ihrer Smartcard und PIN zu authentifizieren. In diesem Thema wird die Implementierung der Transport Layer Security-Client Authentifizierung mit AD FS 2.0 behandelt. Weitere Informationen zu AD FS 2.0 Authentifizierungstypen finden Sie unter AD FS 2.0: Ändern des lokalen Authentifizierungstyps unter [http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384).

<div>


**So konfigurieren Sie AD FS 2.0 zur Unterstützung der Client Authentifizierung**

1.  Melden Sie sich mit einem Domänenadministratorkonto beim AD FS 2.0 Computer an.

2.  Starten Sie Windows Explorer.

3.  Navigieren Sie zu C\\:\\Verzeichnis Inetpub\\adfs ls

4.  Erstellen Sie eine Sicherungskopie der vorhandenen Datei "Internet. config".

5.  Öffnen Sie die vorhandene Datei "Internet. config" mit Editor.

6.  Klicken Sie in der Menüleiste auf **Bearbeiten** , und wählen Sie dann **Suchen**aus.

7.  Suchen Sie ** \<nach\>localAuthenticationTypes**.
    
    Beachten Sie, dass vier Authentifizierungstypen aufgeführt werden: eine pro Reihe.

8.  Verschiebt die Position mit dem TLSClient-Authentifizierungstyp an den Anfang der Liste im Abschnitt.

9.  Speichern und schließen Sie die Datei "Internet. config".

10. Starten Sie eine Eingabeaufforderung mit erhöhten Rechten.

11. Starten Sie IIS neu, indem Sie den folgenden Befehl ausführen:
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

