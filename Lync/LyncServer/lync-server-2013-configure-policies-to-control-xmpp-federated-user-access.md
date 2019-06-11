---
title: 'Lync Server 2013: Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch XMPP-Partnerbenutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure policies to control XMPP federated user access
ms:assetid: 0fe0ff75-e52a-4e3e-923a-64f6412ac4e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552446(v=OCS.15)
ms:contentKeyID: 48679557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ec90a1b079935713ce6f13e7b74763e7004dedf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a>Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch XMPP-Partnerbenutzer in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Diese Dokumentation ist vorläufig und kann geändert werden. Leere Themen sind als Platzhalter enthalten.

Wenn Sie Richtlinien für die Unterstützung von Verbundpartnern des Extensible Messaging and Presence Protocol (XMPP) konfigurieren, gelten die Richtlinien für Benutzer von XMPP-Verbunddomänen, nicht aber für Benutzer von SIP-Chat Diensten (im). (beispielsweise Windows Live) oder SIP-Verbunddomänen. Sie konfigurieren einen **XMPP-Verbund Partner** für jede XMPP-Verbunddomäne, die es Ihren Benutzern ermöglichen soll, Kontakte hinzuzufügen und mit Ihnen zu kommunizieren. Die XMPP-Partner Richtlinien sind nur in einem einzigen Bereich verfügbar, obwohl Sie nicht als globale Richtlinie definiert sind und als globale Richtlinie fungieren. Wenn Sie eine globale, Website-oder Benutzerrichtlinie für XMPP-Verbundpartner definieren möchten, konfigurieren Sie den Richtlinienbereich, indem Sie zunächst die Richtlinie für den externen Zugriff für den erforderlichen Bereich erstellen und konfigurieren. Details zu den Richtlinientypen, die Sie für den externen Zugriff und den Verbund konfigurieren können, finden Sie unter [Verwalten des Föderations-und des externen Zugriffs auf lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in der Betriebsdokumentation.

<div>


> [!NOTE]  
> Alle Richtlinien für den <STRONG>Verbund und den externen Zugriff</STRONG> werden über die in-Band-Bereitstellung angewendet. Die Richtlinien, die für den Benutzer gelten, zu einer Website gehören oder im Bereich Global sind, werden dem Client während der Anmeldung mitgeteilt. Sie können Richtlinien konfigurieren, um den Zugriff auf XMPP-Verbundpartner zu steuern, auch wenn Sie die XMPP-Föderation für Ihre Organisation nicht aktiviert haben. Die von Ihnen konfigurierten Richtlinien werden jedoch nur wirksam, wenn Sie die XMPP-Partner Föderation bereitgestellt, für Ihre Organisation aktiviert und konfiguriert haben. Details zum Bereitstellen und Konfigurieren von XMPP-Partnerverbund finden Sie unter <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Konfigurieren von SIP Federation, XMPP Federation und Public Instant Messaging in lync Server 2013</A> in der Bereitstellungsdokumentation. Wenn Sie eine Benutzerrichtlinie in der Richtlinie für den externen Zugriff zum Steuern von XMPP-Verbundpartnern angeben, gilt die Richtlinie nur für Benutzer, die für lync Server 2013 aktiviert und für die Verwendung der Richtlinie konfiguriert sind.



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a>So bearbeiten Sie eine globale Richtlinie für XMPP-Verbundpartner

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie dann auf **Richtlinie für den externen Zugriff**.

4.  Führen Sie auf der Seite " **Richtlinie für den externen Zugriff** " die folgenden Schritte für die globale Richtlinie aus:

5.  Klicken Sie auf die globale Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf Details anzeigen.

6.  Geben Sie eine Beschreibung für die globale Richtlinie an (optional).

7.  Wählen Sie **Kommunikation mit Verbundbenutzern aktivieren**aus.

8.  Wählen Sie **Kommunikation mit XMPP-Verbundbenutzern aktivieren**aus.

9.  Klicken Sie auf **Commit** , um Ihre Änderungen an der globalen Richtlinie zu speichern.

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a>So erstellen Sie eine Website-oder Benutzerrichtlinie für XMPP-Verbundpartner

1.  Klicken Sie auf **neu**, und klicken Sie dann auf **Website Richtlinie** oder **Benutzerrichtlinie**. Klicken Sie unter **Website auswählen**auf die entsprechende Website in der Liste, und klicken Sie dann auf **OK**.

2.  Geben Sie eine Beschreibung für die Website Richtlinie an (optional).

3.  Wählen Sie in der Website-oder Benutzerrichtlinie die Option **Kommunikation mit Verbundbenutzern aktivieren**aus.

4.  Wählen Sie **Kommunikation mit XMPP-Verbundbenutzern aktivieren**aus.

5.  Klicken Sie auf **Commit** , um Ihre Änderungen an der Website-oder Benutzerrichtlinie zu speichern.

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a>So bearbeiten Sie eine vorhandene Richtlinie für XMPP-Verbundpartner

1.  Wenn Sie eine vorhandene Richtlinie ändern möchten, wählen Sie die entsprechende Richtlinie in der Liste aus, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

2.  Ändern oder aktualisieren Sie die Beschreibung für die Richtlinie (optional).

3.  Aktivieren oder deaktivieren Sie die Option **Kommunikation mit Verbundbenutzern aktivieren**.

4.  Aktivieren oder deaktivieren Sie die Option **Kommunikation mit XMPP-Verbundbenutzern aktivieren**.

5.  Klicken Sie auf **Commit** , um Ihre Änderungen an der Richtlinie zu speichern.

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>So bearbeiten Sie eine vorhandene Richtlinie für XMPP-Verbundpartner mithilfe von Windows PowerShell

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Geben Sie in der lync Server-Verwaltungsshell Folgendes ein:
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Ein Beispielbefehl, mit dem die globale Richtlinie für den Zugriff durch den Verbundbenutzer auf true (aktiviert) und XMPP-Domänenzugriff auf true festgelegt wird (aktiviert):
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a>So erstellen Sie eine Website-oder Benutzerrichtlinie für XMPP-Verbundpartner mithilfe von Windows PowerShell

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Geben Sie in der lync Server-Verwaltungsshell Folgendes ein:
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Ein Beispielbefehl, der eine Website Richtlinie für die Website "Redmond" für den Verbundbenutzer Zugriff auf den aktivierten und XMPP-Domänenzugriff auf "aktiviert" setzt:
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>So löschen Sie eine vorhandene Richtlinie für XMPP-Verbundpartner mithilfe von Windows PowerShell

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Geben Sie in der lync Server-Verwaltungsshell Folgendes ein:
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    Ein Beispielbefehl, mit dem eine Benutzerrichtlinie gelöscht wird:
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  Ein Beispielbefehl, mit dem die globale Richtlinie auf Standardwerte zurückgesetzt wird:
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer zu einem für Lync aktivierten Benutzer in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[Verwalten von XMPP-Verbundpartnern für Ihre Organisation in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Satz-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[Neu – CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

