---
title: 'Lync Server 2013: Konfigurieren von Zertifikaten für den Director'
description: 'Lync Server 2013: Konfigurieren Sie Zertifikate für den Director.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for the Director
ms:assetid: 22988186-15ae-43b1-92f4-0adb3b75a7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398296(v=OCS.15)
ms:contentKeyID: 48183612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cadc3f51b036120e21c3f1e6201f872aacafef69
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578071"
---
# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a>Konfigurieren von Zertifikaten für den Director in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-08_

<div>


> [!IMPORTANT]  
> Wenn Sie den Zertifikat-Assistenten ausführen, müssen Sie mit einem Konto angemeldet sein, das Mitglied einer Gruppe ist, die über die entsprechenden Berechtigungen für den zu verwendeten Zertifikatvorlagentyp verfügt. Standardmäßig wird für eine lync Server 2013 Zertifikatanforderung die Webserverzertifikatvorlage verwendet. Wenn Sie ein Konto verwenden, das Mitglied der RTCUniversalServerAdmins-Gruppe ist, kann mit dieser Vorlage nur ein Zertifikat angefordert werden, wenn dieser Gruppe die zum Verwenden dieser Vorlage erforderlichen Registrierungsberechtigungen erteilt wurden.



</div>

Für jeden Director wird ein Standardzertifikat, ein internes Webzertifikat und ein externes Webzertifikat benötigt. Ausführliche Informationen zu den Zertifikatanforderungen für Directors finden Sie in der Planungsdokumentation unter [Zertifikatanforderungen für interne Server in lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) .

Verwenden Sie das folgende Verfahren, um Director-Zertifikate zu konfigurieren. Wiederholen Sie das Verfahren für jeden Director. Die Schritte in diesem Verfahren beschreiben, wie Sie ein Zertifikat einer internen Stammzertifizierungsstelle konfigurieren, die in Ihrem Unternehmen eingesetzt wird. Zertifikatanforderungen werden in diesem Verfahren offline verarbeitet. Ausführliche Informationen zum Anfordern von Zertifikaten bei einer externen Zertifizierungsstelle erhalten Sie von Ihrem Support-Team.

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a>So konfigurieren Sie Zertifikate für den Director oder Director-Pool

1.  Klicken Sie im lync Server-Bereitstellungs-Assistenten neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen**auf **Ausführen**.

2.  Klicken Sie auf der Seite **Zertifizierungs-Assistent** auf **Anfordern**.

3.  Klicken Sie auf der Seite **Zertifikatanforderung** auf **Weiter**.

4.  Akzeptieren Sie auf der Seite **Verzögerte oder sofortige Anforderungen** die Standardoption **Anforderung unmittelbar an eine Onlinezertifizierungsstelle senden**, und klicken Sie dann auf **Weiter**.

5.  Klicken Sie auf der Seite **Zertifizierungsstelle auswählen** auf die interne Windows-Zertifizierungsstelle, die Sie verwenden möchten, und klicken Sie dann auf **Weiter**.

6.  Geben Sie auf der Seite **Zertifizierungsstellenkonto** alternative Anmeldeinformationen für den Fall an, dass das zur Anmeldung verwendete Konto keine ausreichenden Berechtigungen zum Anfordern des Zertifikats besitzt, und klicken Sie anschließend auf **Weiter**.

7.  Klicken Sie auf der Seite **Alternative Zertifikatvorlage angeben** auf **Weiter**.

8.  Geben Sie auf der Seite **Namens- und Sicherheitseinstellungen** einen Wert für **Anzeigename** ein, akzeptieren Sie die Schlüssellange von 2.048 Bit, und klicken Sie auf **Weiter**.

9.  Überprüfen Sie optional die Informationen auf der Seite **Organisationsinformationen**, und klicken Sie anschließend auf **Weiter**.

10. Überprüfen Sie optional die Informationen auf der Seite **Geografische Informationen**, und klicken Sie anschließend auf **Weiter**.

11. Klicken Sie auf der Seite **Antragstellername/Alternative Antragstellernamen** auf **Weiter**.
    
    <div>
    

    > [!NOTE]  
    > Die Liste der alternativen Antragstellernamen sollte den Namen des Computers enthalten, auf dem Sie den Director installieren (falls nur ein Director vorhanden ist), andernfalls den Namen des Director-Pools und die Namen der einfachen URLs, die für die Organisation konfiguriert wurden.

    
    </div>

12. Wählen Sie auf der Seite **SIP-Domäneneinstellung für alternative Antragstellernamen (SANs)** die Option **Konfigurierte SIP-Domänen** für alle Domänen aus, die der Director verarbeiten soll, und klicken Sie dann auf **Weiter**.

13. Geben Sie auf der Seite **Zusätzliche alternative Antragstellernamen konfigurieren** zusätzlich erforderliche alternative Antragstellernamen an, und klicken Sie auf **Weiter**.

14. Klicken Sie auf der Seite **Zusammenfassung der Zertifikatanforderung** auf **Weiter**.

15. Klicken Sie auf der Seite **Befehle ausführen** nach Abschluss der Befehlsausführung auf **Weiter**.

16. Klicken Sie auf der Seite **Status der Onlinezertifikatanforderung** auf **Fertig stellen**.

17. Klicken Sie auf der Seite **Zertifikatzuweisung** auf **Weiter**.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie das Zertifikat anzeigen möchten, doppelklicken Sie auf das Zertifikat in der Liste.

    
    </div>

18. Klicken Sie auf der Seite **Zusammenfassung der Zertifikatzuweisung** auf **Weiter**.

19. Klicken Sie auf der Seite **Befehle ausführen** nach Abschluss der Befehlsausführung auf **Fertig stellen**.

20. Klicken Sie auf der Seite **Zertifizierungs-Assistent** auf **Schließen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

