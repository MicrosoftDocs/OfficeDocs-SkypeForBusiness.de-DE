---
title: 'Lync Server 2013: Konfigurieren der Benutzerkontoeinstellungen'
description: 'Lync Server 2013: Konfigurieren der Benutzerkontoeinstellungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure user account settings
ms:assetid: b7c74ecc-b924-4efc-8a56-3a5f94a9ef13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412896(v=OCS.15)
ms:contentKeyID: 48185200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6ab4c57ba3d3e8c084314e1093736334312d0c1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577511"
---
# <a name="configure-user-account-settings-in-lync-server-2013"></a>Konfigurieren von Benutzerkontoeinstellungen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-05_

Teilnehmer an Einwahlkonferenzen geben ihre Telefonnummer oder Durchwahl sowie eine PIN ein, um als authentifizierte Benutzer an Konferenzen teilzunehmen. Der in lync Server Benutzerkonten angegebene Telefonie- **Anschluss-URI** ist für die Authentifizierung erforderlich.

In diesem Thema wird beschrieben, wie Sie einem einzelnen Benutzerkonto einen **Anschluss-URI** zuweisen. Wenn Sie mehreren Benutzerkonten einen **Anschluss-URI** zuweisen möchten, können Sie ein Skript erstellen, das das Cmdlet **Set-CsUser** verwendet. Ausführliche Informationen zur Verwendung eines Beispielskripts zum Zuweisen von Verbindungs- **URI** zu mehreren Benutzerkonten finden Sie unter "Zuweisen von Verbindungs-URIs zu mehreren Benutzern" unter [https://go.microsoft.com/fwlink/p/?linkId=196945](https://go.microsoft.com/fwlink/p/?linkid=196945) .

<div>

## <a name="to-configure-user-account-settings"></a>So konfigurieren Sie die Benutzerkontoeinstellungen

1.  Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle **Cs-UserAdministrator** oder **CsAdministrator** an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Geben Sie in das Suchfeld den Namen des Benutzers ein, den Sie für Einwahlkonferenzen konfigurieren möchten, oder klicken Sie auf **Filter hinzufügen**, um Suchfelder anzugeben, und klicken Sie dann auf **Suchen**.

5.  Doppelklicken Sie auf den Benutzernamen, um das Dialogfeld **Benutzer lync Server bearbeiten** zu öffnen.

6.  Geben Sie unter **Telefonie** in das Feld **Anschluss-URI** eine eindeutige, normalisierte Telefonnumer ein (beispielsweise tel:+14255550200).
    
    <div>
    

    > [!NOTE]  
    > Sie können den <STRONG>Anschluss-URI</STRONG> nur angeben, wenn die <STRONG>Telefonie</STRONG> nur auf <STRONG>PC-zu-PC</STRONG>, <STRONG>Enterprise-VoIP</STRONG>, <STRONG>Remoteanrufsteuerung</STRONG> oder <STRONG>Remoteanrufsteuerung</STRONG>festgelegt ist.

    
    </div>

7.  Klicken Sie auf **Commit ausführen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

