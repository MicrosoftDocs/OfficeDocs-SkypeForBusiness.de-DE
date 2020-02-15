---
title: 'Lync Server 2013: Erstellen neuer Konfigurationseinstellungen für den Webdienst'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create new Web Service configuration settings
ms:assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182605(v=OCS.15)
ms:contentKeyID: 48185801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e91246feaad4d5375f7f7a93597f9bc754e7b613
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007114"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-new-web-service-configuration-settings-in-lync-server-2013"></a>Erstellen neuer Konfigurationseinstellungen für den Webdienst in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Sie können die Seite **Webdienst** verwenden, um die Authentifizierungsmethoden für den Zugriff auf lync Server 2013 zugehörige Webserver und Webdienste zu konfigurieren.

Führen Sie die folgenden Schritte aus, um eine neue webdienstrichtlinie zu erstellen.

<div>

## <a name="to-create-new-web-service-configuration-settings"></a>So erstellen Sie neue Webdienste-Konfigurationseinstellungen

1.  Melden Sie sich von einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe (oder gleichwertigen Benutzerrechten) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Webdienst**.

4.  Klicken Sie auf der Seite **Webdienst** auf **neu**, und führen Sie eine der folgenden Aktionen aus:
    
      - Klicken Sie auf **Websitekonfiguration**, um den Webdienst für eine Website zu konfigurieren. Klicken Sie unter **Standort auswählen**auf den Standort, auf den die webdienstrichtlinie angewendet werden soll, und klicken Sie dann auf **OK**.
    
      - Klicken Sie zum Konfigurieren des Webdiensts für einen Pool auf **Poolkonfiguration**. Klicken Sie unter **Dienst auswählen**auf den Dienst, auf den die webdienstrichtlinie angewendet wird, und klicken Sie auf **OK**.

5.  Wählen Sie unter **neue Webdienst Einstellung**unter **integrierte Windows-Authentifizierung**die **Option Aushandeln**, **integrierte Windows-Authentifizierung**oder **keine**aus.

6.  Wählen Sie je nach Funktionen der Clients und der Unterstützung in Ihrer Umgebung, eine oder mehrere der folgenden Optionen:
    
      - **PIN-Authentifizierung aktivieren** – Clients werden über eine PIN authentifiziert.
    
      - **Zertifikatauthentifizierung aktivieren** – Die Server im Pool geben Zertifikate an die Clients aus.
    
      - **Download einer Zertifikatkette aktivieren** – Server können die Zertifikatkette für das jeweilige Zertifikat herunterladen.

7.  Klicken Sie auf **Commit ausführen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

