---
title: 'Lync Server 2013: Erstellen oder Ändern von Netzwerk Websites'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network sites
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520975(v=OCS.15)
ms:contentKeyID: 48183801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c77c343bff92e25ffc1678bc06e7a0ef05d3f96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a>Erstellen oder Ändern von Netzwerk Websites in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-08_

Netzwerk Websites sind die Büros oder Standorte, die in den einzelnen Regionen einer Anrufannahme Steuerung oder erweiterten 9-1-1-Bereitstellung konfiguriert sind. Sie können die Microsoft lync Server 2013-Systemsteuerung verwenden, um Websites zu konfigurieren und Sie mit Regionen zu verknüpfen. Beispielsweise kann eine netzwerkregion für Nordamerika mit Netzwerken wie Chicago, Redmond und Vancouver verknüpft sein. Eine CAC-Netzwerk Website muss für jede Website innerhalb einer Organisation erstellt werden, selbst wenn diese Website keine Bandbreiteneinschränkungen aufweist. In der lync Server-Systemsteuerung können Sie Netzwerk Websites erstellen, ändern und löschen. Gehen Sie wie folgt vor, um eine Netzwerk Website zu erstellen oder zu ändern. Details zum Löschen einer vorhandenen Netzwerk Website finden Sie unter [Löschen einer vorhandenen Netzwerk Website in lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).

<div>

## <a name="to-create-a-network-site"></a>So erstellen Sie eine Netzwerk Website

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** , und klicken Sie dann auf **Website**.

4.  Klicken Sie auf der Seite **Website** auf **neu**.

5.  Geben Sie auf der **neuen Website**im Feld **Name** einen Namen für diese Website ein.
    
    <div>
    

    > [!NOTE]  
    > Websitenamen müssen innerhalb der lync Server 2013-Bereitstellung eindeutig sein.

    
    </div>

6.  Wählen Sie in der Dropdownliste **Region** einen Netzwerkbereich aus, der dieser Website zugeordnet werden soll.

7.  Optional Wenn Sie Bandbreiteneinschränkungen für Audio-oder Videoanrufe an diese Website vornehmen möchten, wählen Sie das bandbreitenrichtlinienprofil mit den entsprechenden Einstellungen in der Dropdownliste **bandbreitenrichtlinie** aus.
    
    <div>
    

    > [!NOTE]  
    > Auf der Seite " <STRONG>Richtlinienprofil</STRONG> " der Gruppe " <STRONG>Netzwerkkonfiguration</STRONG> " können Sie die Details der verfügbaren bandbreitenrichtlinienprofile anzeigen oder ein neues bandbreitenrichtlinienprofil erstellen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">erstellen oder Ändern von Bandbreitenrichtlinien Profilen in lync Server 2013</A>.

    
    </div>

8.  Optional Wenn Sie die Standorteinstellungen für diese Website angeben möchten, wählen Sie in der Dropdownliste **Standortrichtlinie** eine Standortrichtlinie aus.
    
    <div>
    

    > [!NOTE]  
    > Die Standortrichtlinie weist der Website bestimmte erweiterte 9-1-1-Einstellungen (E9-1-1) und Clientstandort Einstellungen zu. Sie können die Details der verfügbaren Standortrichtlinien anzeigen oder eine neue Standortrichtlinie erstellen, die sich auf der Seite " <STRONG>Standortrichtlinie</STRONG> " der Gruppe " <STRONG>Netzwerkkonfiguration</STRONG> " befindet. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-viewing-location-policy-information.md">Anzeigen von Standortrichtlinien Informationen in lync Server 2013</A>.

    
    </div>

9.  Optional Geben Sie im Feld **Beschreibung** einen Wert ein, um weitere Informationen zu dieser Website bereitzustellen, die nicht allein durch den Namen ausgedrückt werden können.

10. Klicken Sie auf **Commit ausführen**.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie eine neue Netzwerk Website erstellen, verwenden Sie die Tabelle <STRONG>zugeordnete Subnetze</STRONG> nicht. Sie verknüpfen ein Subnetz mit einer Website, wenn Sie das Subnetz erstellen oder ändern. Ausführliche Informationen finden Sie unter Erstellen oder Ändern von Netzwerk-Subnetzen <A href="lync-server-2013-create-or-modify-network-subnets.md">in lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a>So ändern Sie eine Netzwerk Website

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** , und klicken Sie dann auf **Website**.

4.  Klicken Sie auf der Seite **Website** auf die Website, die Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Auf der Seite " **Website bearbeiten** " können Sie die Beschreibung, die Region, das bandbreitenrichtlinienprofil und die der Website zugeordnete Standortrichtlinie ändern. Ausführliche Informationen finden Sie weiter oben in diesem Thema unter "So erstellen Sie eine Netzwerk Website".

7.  Klicken Sie auf **Commit ausführen**.

Auf dieser Seite können Sie die Tabelle **zugeordnete Subnets** nicht ändern. Die Liste der zugeordneten Subnetze wird als Referenz bereitgestellt, damit Sie wissen, welche Subnetze betroffen sind, wenn Sie die Websiteeinstellungen ändern.

</div>

<div>

## <a name="to-delete-a-network-site"></a>So löschen Sie eine Netzwerk Website

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** , und klicken Sie dann auf **Website**.

4.  Klicken Sie auf der Seite **Website** auf die Website, die Sie löschen möchten.
    
    <div>
    

    > [!NOTE]  
    > Sie können mehr als eine Website gleichzeitig löschen. Drücken Sie dazu STRG, und wählen Sie mehrere Websites aus, während Sie die STRG-Taste gedrückt halten. Wenn Sie alle Websites auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG> .

    
    </div>

5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie auf **OK**.
    
    <div>
    

    > [!WARNING]  
    > Sie können eine Netzwerk Website nicht entfernen, wenn Sie einem Netzwerk-Subnetz zugeordnet ist. Wenn Sie versuchen, eine Website zu entfernen, die einem Subnetz zugeordnet ist, wird eine Fehlermeldung angezeigt. Wenn Sie feststellen möchten, ob eine Website mit Subnetzen verknüpft ist, klicken Sie auf die Website, und klicken Sie dann im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Details anzeigen</STRONG> .

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Löschen einer vorhandenen Netzwerk Website in lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md)  


[New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[Set-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[Remove-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

