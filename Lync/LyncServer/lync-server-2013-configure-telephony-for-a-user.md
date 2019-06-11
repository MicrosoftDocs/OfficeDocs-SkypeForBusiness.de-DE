---
title: 'Lync Server 2013: Konfigurieren der Telefonie für einen Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure telephony for a user
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520988(v=OCS.15)
ms:contentKeyID: 48183987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97f4fc79b871a962fe498d6dbd908b75f6b2fecd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-telephony-for-a-user-in-lync-server-2013"></a>Konfigurieren der Telefonie für einen Benutzer in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Telefonieeinstellungen sind einige der individuellen Einstellungen eines Benutzerkontos, das in der lync Server-Systemsteuerung für den Benutzer konfiguriert werden kann (das heißt, wenn der einzelne Benutzer für lync Server 2013 aktiviert wurde und die Organisation die Telefonie unterstützt).

Zu den lync Server-Benutzer Telefonie-Optionen gehören die folgenden:

  - **Audio/Video deaktiviert**   der Benutzer kann mit Audio und Video keine Anrufe tätigen.

  - **Nur PC-zu-PC**   der Benutzer kann nur PC-zu-PC-Audio-oder Videoanrufe tätigen.

  - **Enterprise-VoIP**   der Benutzer kann die lync Server 2013-Infrastruktur verwenden, um alle eingehenden und ausgehenden Anrufe weiterzuleiten. Der Benutzer kann auch PC-zu-PC-Anrufe tätigen.

  - **Remote Anrufsteuerung**   der Benutzer kann lync Server 2013 verwenden, um das Desktoptelefon zu steuern, und kann auch PC-zu-PC-Anrufe tätigen.

Details zum Konfigurieren der Telefonie für eine Organisation finden Sie unter [Konfigurieren der Telefonie für einen Benutzer in lync Server 2013](lync-server-2013-configure-telephony-for-a-user.md) und [Bereitstellen von Enterprise-VoIP in lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in der Bereitstellungsdokumentation.

<div>

## <a name="to-configure-telephony-for-a-specific-user-account"></a>So konfigurieren Sie die Telefonie für ein bestimmtes Benutzerkonto

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Geben Sie im Feld **Benutzer suchen** den gesamten oder den ersten Teil des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontos (Security Accounts Manager), der SIP-Adresse oder des Uniform Resource Identifier (URI) des gewünschten Benutzerkontos ein, und klicken Sie dann auf **suchen. **.

5.  Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie ändern möchten.

6.  Klicken Sie im Menü **Bearbeiten** auf **ändern**.

7.  Führen Sie in **Telefonie**die folgenden Aktionen aus:
    
      - Wenn Sie Audio-und Videoanrufe für den Benutzer deaktivieren möchten, klicken Sie auf **Audio/Video deaktiviert**.
    
      - Wenn Sie die PC-zu-PC-Audiokommunikation für den Benutzer, aber nicht die Remoteanrufsteuerung oder Enterprise-VoIP aktivieren möchten, klicken Sie auf **nur PC-zu-** PC. Geben Sie einen Wert für den Leitungs- **URI** für das Telefon an, das der Benutzer für die PC-zu-PC-Audiokommunikation verwendet.
    
      - Klicken Sie auf **Enterprise-VoIP**, um die Telefonanrufe des Benutzers mithilfe der lync Server 2010-Infrastruktur in Übereinstimmung mit der Service Richtlinienklasse zu leiten, einschließlich PC-zu-PC-Audiokommunikation. Geben Sie in der **Zeile URI**die Telefonnummer für Enterprise-VoIP an. Geben Sie in der Richtlinie für **Wähl Plan Richtlinien** und **VoIP**die entsprechenden Richtlinien für den Benutzer an. Wenn Sie die Normalisierungsregeln für die Übersetzung von Telefonnummern angeben möchten, die vom Benutzer im E. 164-Format gewählt wurden, wählen Sie das entsprechende Standortprofil in der **ortungsrichtlinie**aus.
    
      - Klicken Sie auf **Remoteanrufsteuerung**, um die Remoteanrufsteuerung zu aktivieren, mit der Benutzer Ihre Desktop-Telefonleitung von lync Server 2013 steuern können, um PC-zu-PC-Anrufe zu tätigen und PC-zu-Telefon-Anrufe zu tätigen. Geben Sie in der **Zeile URI**die Telefonnummer für die Remoteanrufsteuerung ein. Der Benutzer muss über ein Desktoptelefon und eine PBX-Verbindung (Private Branch Exchange) für das Anrufrouting verfügen.

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

