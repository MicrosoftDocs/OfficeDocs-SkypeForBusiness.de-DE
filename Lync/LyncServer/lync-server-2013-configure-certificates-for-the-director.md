---
title: 'Lync Server 2013: Konfigurieren von Zertifikaten für den Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure certificates for the Director
ms:assetid: 22988186-15ae-43b1-92f4-0adb3b75a7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398296(v=OCS.15)
ms:contentKeyID: 48183612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d2da30923231087e706e2a969fdba2884361f6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839415"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a>Konfigurieren von Zertifikaten für den Director in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

<div>


> [!IMPORTANT]  
> Wenn Sie den Zertifikat-Assistenten ausführen, stellen Sie sicher, dass Sie mit einem Konto angemeldet sind, das Mitglied einer Gruppe ist, der die entsprechenden Berechtigungen für den Typ der Zertifikatvorlage zugewiesen wurden, die Sie verwenden werden. Standardmäßig verwendet eine lync Server 2013-Zertifikatanforderung die Webserverzertifikatvorlage. Wenn Sie ein Konto verwenden, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist, um ein Zertifikat mithilfe dieser Vorlage anzufordern, stellen Sie sicher, dass der Gruppe die für die Verwendung dieser Vorlage erforderlichen Registrierungsberechtigungen zugewiesen wurden.



</div>

Für jeden Director ist ein Standardzertifikat, ein webinternes Zertifikat und ein externes Webzertifikat erforderlich. Details zu den Zertifikatanforderungen für Directors finden Sie unter [Zertifikatanforderungen für interne Server in lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in der Planungsdokumentation.

Gehen Sie wie folgt vor, um Director-Zertifikate zu konfigurieren. Wiederholen Sie den Vorgang für jeden Director. In den Schritten dieses Verfahrens wird beschrieben, wie Sie ein Zertifikat von einer internen Unternehmensstammzertifizierungsstelle, die von Ihrer Organisation bereitgestellt wird, und mit der Offline Anforderungsverarbeitung konfigurieren. Informationen zum Abrufen von Zertifikaten von einer externen Zertifizierungsstelle erhalten Sie von Ihrem Support Team.

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a>So konfigurieren Sie Zertifikate für den Director-oder Director-Pool

1.  Klicken Sie im lync Server-Bereitstellungs-Assistenten neben **Schritt 3: anfordern, installieren oder Zuweisen von Zertifikaten**auf **Ausführen**.

2.  Klicken Sie auf der Seite **Zertifikat-Assistent** auf **Anfordern**.

3.  Klicken Sie auf der Seite **Zertifikatanforderung** auf **weiter**.

4.  Übernehmen Sie auf der Seite **verzögerte oder sofortige Anforderungen** die Option Standard **Anforderung sofort an eine Onlinezertifizierungsstelle senden** , und klicken Sie dann auf **weiter**.

5.  Klicken Sie auf der Seite **Zertifizierungsstelle auswählen** auf die interne Windows-Zertifizierungsstelle, die Sie verwenden möchten, und klicken Sie dann auf **weiter**.

6.  Geben Sie auf der Seite Zertifizierungsstellen **Konto** die zu verwendenden alternativen Anmeldeinformationen an, wenn das Konto, mit dem Sie angemeldet sind, nicht über die erforderlichen Berechtigungen zum Anfordern des Zertifikats verfügt, und klicken Sie dann auf **weiter**.

7.  Klicken Sie auf der Seite **Alternative Zertifikatvorlage angeben** auf **weiter**.

8.  Auf der Seite **Name und Sicherheitseinstellungen** können Sie einen **Anzeigenamen**angeben, die 2048-Bit-Schlüssellänge akzeptieren und dann auf **weiter**klicken.

9.  Geben Sie auf der Seite **Organisationsinformationen** optional Organisationsinformationen an, und klicken Sie dann auf **weiter**.

10. Geben Sie auf der Seite **geographische Informationen** optional geografische Informationen an, und klicken Sie dann auf **weiter**.

11. Klicken Sie auf der Seite **Betreffname/Subject Alternative Names** auf **weiter**.
    
    <div>
    

    > [!NOTE]  
    > Die Liste Subject Alternative Name sollte den Namen des Computers enthalten, auf dem Sie den Director installieren (falls ein einzelner Director) oder der Name des Director-Pools und die für die Organisation konfigurierten einfachen URL-Namen.

    
    </div>

12. Wählen Sie in der **SIP-Domäneneinstellung auf der Seite Subject Alternate Names (SANs)** die **konfigurierten SIP-Domänen** für alle Domänen aus, die der Director behandeln soll, und klicken Sie dann auf **weiter**.

13. Fügen Sie auf der Seite **configure additional Subject Alternative Names** alle weiteren erforderlichen alternativen Antragstellernamen hinzu, und klicken Sie dann auf **weiter**.

14. Klicken Sie auf der Seite **Zusammenfassung der Zertifikatanforderung** auf **weiter**.

15. Klicken Sie auf der Seite **ausführende Befehle** auf **weiter** , nachdem die Befehle ausgeführt wurden.

16. Klicken Sie auf der Seite **Online Zertifikat Anforderungs Status** auf **Fertig stellen**.

17. Klicken Sie auf der Seite **zertifikatzuweisung** auf **weiter**.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie das Zertifikat anzeigen möchten, doppelklicken Sie in der Liste auf das Zertifikat.

    
    </div>

18. Klicken Sie auf der Seite **Zertifikat Zuordnungszusammenfassung** auf **weiter**.

19. Klicken Sie auf der Seite **Ausführungsbefehle** auf **Fertig stellen** , nachdem die Ausführung der Befehle abgeschlossen ist.

20. Klicken Sie auf der Seite des **Zertifikat-Assistenten** auf **Schließen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

