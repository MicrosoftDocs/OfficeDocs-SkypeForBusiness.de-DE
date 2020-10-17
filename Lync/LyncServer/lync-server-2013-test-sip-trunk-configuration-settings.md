---
title: 'Lync Server 2013: Testen der SIP-Trunk-Konfigurationseinstellungen'
description: 'Lync Server 2013: Testen der SIP-Trunk-Konfigurationseinstellungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test SIP trunk configuration settings
ms:assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721880(v=OCS.15)
ms:contentKeyID: 49733814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d44fe2ef5123bec31fafaff2d811a501e5cca4a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558271"
---
# <a name="test-sip-trunk-configuration-settings-in-lync-server-2013"></a>Testen von Konfigurationseinstellungen für SIP-Trunks in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Mit SIP-Trunk-Konfigurationseinstellungen werden die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Nebenstellenanlage (Private Branch Exchange, PBX) oder einem SBC (Session Border Controller) des Dienstanbieters definiert. Mit diesen Einstellungen kann Folgendes angegeben werden:

  - Ob die Medienumgebung für Trunks aktiviert werden soll.

  - Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control-Protokoll) gesendet werden.

  - Ob für jeden Trunk die SRTP-Verschlüsselung (Secure Real-Time-Protokoll) erforderlich ist.

Wenn Sie Microsoft lync Server 2013 installieren, wird eine globale Sammlung von SIP-trunkkonfigurationseinstellungen für Sie erstellt. Außerdem können Administratoren benutzerdefinierte Einstellungssammlungen auf Standortebene oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst). Administratoren können auch das Test-CsTrunkConfiguration-Cmdlet verwenden, um zu überprüfen, ob ein trunk eine Nummer, die von einem Benutzer gewählt wurde, in eine Nummer umwandeln kann, die vom Gateway verarbeitet werden kann.

Trunk-Konfigurationseinstellungen können nur mit Windows PowerShell und dem Cmdlet [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) getestet werden. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-test-sip-trunk-configuration-settings"></a>So testen Sie die SIP-Trunk-Konfigurationseinstellungen

  - Mit diesem Befehl wird überprüft, ob die trunkkonfigurationseinstellungen für den Standort "Redmond" die gewählte Nummer 4255551212 ordnungsgemäß konvertieren können.
    
        $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
        Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk

</div>

</div>

<span> </span>

</div>

</div>

</div>

