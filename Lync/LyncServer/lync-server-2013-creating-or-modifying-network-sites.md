---
title: 'Lync Server 2013: Erstellen oder Ändern von Netzwerkstandorten'
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
ms.openlocfilehash: 5d95073a590b9e5ddde54df4f77cd15e936234d0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a>Erstellen oder Ändern von Netzwerkstandorten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-08_

Netzwerkstandorte sind Büros, Niederlassungen oder Standorte, die in jeder Region einer Bereitstellung für einen Anrufsteuerungsdienst oder Notfalldienst (E9-1-1) konfiguriert sind. Sie können die Microsoft lync Server 2013-Systemsteuerung verwenden, um Websites zu konfigurieren und Sie Regionen zuzuordnen. Eine Netzwerkregion für Nordamerika ist beispielsweise Netzwerkstandorten wie Chicago, Redmond und Vancouver zugeordnet. Ein Anrufsteuerungsdienst-Netzwerkstandort muss für jeden Standort einer Organisation erstellt werden, selbst wenn der jeweilige Standort keine Bandbreiteneinschränkungen aufweist. In der lync Server-Systemsteuerung können Sie Netzwerkstandorte erstellen, ändern und löschen. Verwenden Sie das folgende Verfahren, um einen Netzwerkstandort zu erstellen oder zu ändern. Ausführliche Informationen zum Löschen eines vorhandenen Netzwerkstandorts finden Sie unter [Löschen eines vorhandenen Netzwerkstandorts in lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).

<div>

## <a name="to-create-a-network-site"></a>So erstellen Sie einen Netzwerkstandort

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Standort**.

4.  Klicken Sie auf der Seite **Standort** auf **Neu**.

5.  Geben Sie unter **Neuer Standort** im Feld **Name** einen Namen für den Standort ein.
    
    <div>
    

    > [!NOTE]  
    > Websitenamen müssen innerhalb der lync Server 2013-Bereitstellung eindeutig sein.

    
    </div>

6.  Wählen Sie in der Dropdownliste **Region** eine Netzwerkregion aus, die diesem Standort zugeordnet werden soll.

7.  (Optional) Wenn Sie Bandbreitenbeschränkungen für Audio- oder Videoanrufe für diesen Standort festlegen möchten, wählen Sie das Bandbreitenrichtlinienprofil mit den passenden Einstellungen in der Dropdownliste **Bandbreitenrichtlinie** aus.
    
    <div>
    

    > [!NOTE]  
    > Auf der Seite <STRONG>Richtlinienprofil</STRONG> in der Gruppe <STRONG>Netzwerkkonfiguration</STRONG> können Sie die Details der verfügbaren Bandbreitenrichtlinienprofile anzeigen oder ein neues Bandbreitenrichtlinienprofil erstellen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">erstellen oder Ändern von Bandbreitenrichtlinien Profilen in lync Server 2013</A>.

    
    </div>

8.  (Optional) Wenn Sie Ortungseinstellungen für diesen Standort bereitstellen möchten, wählen Sie in der Dropdownliste **Ortungsrichtlinie** eine Ortungsrichtlinie aus.
    
    <div>
    

    > [!NOTE]  
    > Die Ortungsrichtlinie weist dem Standort bestimmte E9-1-1- und Clientstandorteinstellungen zu. Auf der Seite <STRONG>Ortungsrichtlinie</STRONG> in der Gruppe <STRONG>Netzwerkkonfiguration</STRONG> können Sie die Details der verfügbaren Ortungsrichtlinien anzeigen oder eine neue Ortungsrichtlinie erstellen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-viewing-location-policy-information.md">Anzeigen von Informationen zu Standortrichtlinien in lync Server 2013</A>.

    
    </div>

9.  (Optional) Geben Sie im Feld **Beschreibung** einen Wert zum Bereitstellen weiterer Informationen zu diesem Standort ein, die nicht durch den Namen allein vermittelt werden können.

10. Klicken Sie auf **Commit**.
    
    <div>
    

    > [!NOTE]  
    > Beim Erstellen eines neuen Netzwerkstandorts verwenden Sie nicht die Tabelle <STRONG>Zugeordnete Subnetze</STRONG>. Sie ordnen einem Standort ein Subnetz zu, wenn Sie das Subnetz erstellen oder ändern. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-create-or-modify-network-subnets.md">erstellen oder Ändern von Netzwerk Subnetzen in lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a>So ändern Sie einen Netzwerkstandort

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Standort**.

4.  Klicken Sie auf der Seite **Standort** auf den Standort, den Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Auf der Seite **Standort bearbeiten** können Sie die Beschreibung, die Region, das Bandbreitenrichtlinienprofil und die Ortungsrichtlinie für den Standort ändern. Ausführliche Informationen hierzu finden Sie unter "So erstellen Sie einen Netzwerkstandort" weiter oben in diesem Thema.

7.  Klicken Sie auf **Commit**.

Sie können die Tabelle **Zugeordnete Subnetze** auf dieser Seite nicht ändern. Die Liste der zugeordneten Subnetze wird zu Referenzzwecken angezeigt, damit Sie wissen, auf welche Subnetze sich die Änderung der Standorteinstellungen auswirkt.

</div>

<div>

## <a name="to-delete-a-network-site"></a>So löschen Sie einen Netzwerkstandort

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Standort**.

4.  Klicken Sie auf der Seite **Standort** auf den Standort, den Sie löschen möchten.
    
    <div>
    

    > [!NOTE]  
    > Sie können mehrere Standorte in einem Arbeitsschritt löschen. Drücken Sie hierzu STRG, und wählen Sie bei gedrückter STRG-TASTE mehrere Standorte aus. Wenn Sie alle Standorte auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG>.

    
    </div>

5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie auf **OK**.
    
    <div>
    

    > [!WARNING]  
    > Ein Netzwerkstandort kann nicht gelöscht werden, wenn er einem Netzwerksubnetz zugeordnet ist. Wenn Sie versuchen, einen einem Subnetz zugeordneten Standort zu entfernen, wird eine Fehlermeldung ausgegeben. Um zu überprüfen, ob ein Standort einem Subnetz zugeordnet ist, klicken Sie auf den Standort und anschließend im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Details anzeigen</STRONG>.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Löschen eines vorhandenen Netzwerkstandorts in lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md)  


[New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[Gruppe-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[Remove-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

