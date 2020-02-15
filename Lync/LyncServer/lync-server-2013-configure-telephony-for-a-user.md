---
title: 'Lync Server 2013: Konfigurieren der Telefonie für einen Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure telephony for a user
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520988(v=OCS.15)
ms:contentKeyID: 48183987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cac7f13d7ba46b9affee1f4d44dd56b167597b80
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-telephony-for-a-user-in-lync-server-2013"></a>Konfigurieren der Telefonie für einen Benutzer in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Die Telefonieeinstellungen sind einige der individuellen Einstellungen eines Benutzerkontos, die in lync Server-Systemsteuerung für den Benutzer konfiguriert werden können (das heißt, wenn der einzelne Benutzer für lync Server 2013 aktiviert wurde und die Organisation Telefonie unterstützt).

Lync Server Benutzer Telefonie-Optionen umfassen Folgendes:

  - **Audio/Video deaktiviert**   der Benutzer kann keine Anrufe mit Audio und Video durchführen.

  - **Nur PC-zu-PC**   der Benutzer kann nur PC-zu-PC-Audio-oder-Videoanrufe tätigen.

  - **Enterprise-VoIP**   der Benutzer kann die lync Server 2013-Infrastruktur verwenden, um alle eingehenden und ausgehenden Anrufe weiterzuleiten. Außerdem kann der Benutzer Anrufe von PC zu PC tätigen.

  - **Remote Anrufsteuerung**   der Benutzer kann lync Server 2013 verwenden, um das Desktoptelefon zu steuern, und kann auch PC-zu-PC-Anrufe tätigen.

Ausführliche Informationen zum Konfigurieren der Telefonie für eine Organisation finden Sie unter [Konfigurieren der Telefonie für einen Benutzer in lync Server 2013](lync-server-2013-configure-telephony-for-a-user.md) und [Bereitstellen von Enterprise-VoIP in lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in der Bereitstellungsdokumentation.

<div>

## <a name="to-configure-telephony-for-a-specific-user-account"></a>So konfigurieren Sie Telefonieoptionen für ein bestimmtes Benutzerkonto

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des gewünschten Benutzerkontos ein, und klicken Sie dann auf **Suchen**.

5.  Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie ändern möchten.

6.  Klicken Sie im Menü **Bearbeiten** auf **Ändern**.

7.  Führen Sie im Dialogfeld **Telefonie** die folgenden Schritte aus:
    
      - Klicken Sie zum Deaktivieren von Audio- und Videoanrufen für den Benutzer auf **Audio/Video deaktiviert**.
    
      - Wenn Sie für den Benutzer die Audiokommunikation von PC zu PC, jedoch nicht die Remoteanrufsteuerung oder Enterprise-VoIP aktivieren möchten, klicken Sie auf **Nur PC zu PC**. Geben Sie einen Wert für **Anschluss-URI** für das Telefon an, das der Benutzer für die Audiokommunikation von PC zu PC verwendet.
    
      - Klicken Sie auf **Enterprise-VoIP**, um die Telefonanrufe des Benutzers mithilfe der lync Server 2010-Infrastruktur gemäß der Dienstleistungsklasse-Richtlinie weiterzuleiten, einschließlich der PC-zu-PC-Audiokommunikation. Geben Sie unter **Anschluss-URI** die Telefonnummer für Enterprise-VoIP an. Geben Sie unter **Richtlinie für Wähleinstellungen** und **VoIP-Richtlinie** die entsprechenden Richtlinien für den Benutzer an. Wählen Sie unter **Ortungsrichtlinie** das angemessene Standortprofil aus, um die Normalisierungsregeln für die Übersetzung der vom Benutzer gewählten Telefonnummern in das E.164-Format anzugeben.
    
      - Klicken Sie zum Aktivieren der Remoteanrufsteuerung, mit der Benutzer Ihre Desktop-Telefonleitung von lync Server 2013 aus steuern können, um PC-zu-PC-Anrufe und Anrufe von PC zu Telefon zu tätigen, auf **Remoteanrufsteuerung**. Geben Sie unter **Leitungs-URI**die Telefonnummer für die Remoteanrufsteuerung an. Der Benutzer muss über eine Telefon-und PBX-Verbindung (Private Branch Exchange) für die Anrufweiterleitung verfügen.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Ändern von Benutzerkontoeigenschaften in lync Server 2013](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

