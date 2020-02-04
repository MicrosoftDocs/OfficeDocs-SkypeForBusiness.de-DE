---
title: Ändern von VoIP-Routen zur Verwendung des neuen lync Server 2013-Vermittlungsservers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change voice routes to use the new Lync Server 2013 Mediation Server
ms:assetid: acd487b3-377c-46bf-9f71-fe6152002664
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205162(v=OCS.15)
ms:contentKeyID: 48185069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40f9bed4262adcabdb23e5b5b85e7de43292d18b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a>Ändern von VoIP-Routen zur Verwendung des neuen lync Server 2013-Vermittlungsservers

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

Bei diesem Verfahren werden die VoIP-Routen so geändert, dass der lync Server 2013-Vermittlungsserver anstelle des Legacy Office Communications Server 2007 R2-Vermittlungsservers verwendet wird.

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a>So ändern Sie die VoIP-Routen zur Verwendung des neuen Vermittlungsservers

1.  Systemsteuerung für Lync Server 2013

2.  Wählen Sie im linken Bereich die Option **VoIP-Routing** und dann **Route**aus.

3.  Klicken Sie auf **neu** , um eine neue VoIP-Route zu erstellen.

4.  Füllen Sie die folgenden Felder aus:
    
      - **Name**: Geben Sie einen aussagekräftigen Namen für die VoIP-Route ein. Für dieses Dokument werden wir **W15PSTNRoute**verwenden.
    
      - **Beschreibung**: Geben Sie eine kurze Beschreibung der VoIP-Route ein.

5.  Überspringen Sie alle verbleibenden Abschnitte, bis Sie **zugeordnete Gateways**erreichen. Klicken Sie auf **Hinzufügen**. Wählen Sie das neue Standardgateway aus, und klicken Sie auf **OK**.

6.  Klicken Sie unter **zugeordnete PSTN-Nutzungen**auf **auswählen**.

7.  Wählen Sie auf der Seite **PSTN-Verwendungsdaten Satz auswählen** einen Datensatznamen aus, und klicken Sie dann auf **OK**.

8.  Klicken Sie auf der Seite **neue VoIP-Route** auf **OK** , um die **VoIP-Route**zu erstellen.

9.  Wählen Sie auf der Seite **VoIP-Routing** die Option **Route**aus.

10. Verschieben Sie die neu erstellte Route an den Anfang der Liste, und wählen Sie dann **Commit**aus.

</div>

</div>

<span> </span>

</div>

</div>

</div>

