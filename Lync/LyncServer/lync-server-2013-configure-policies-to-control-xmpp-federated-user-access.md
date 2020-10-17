---
title: 'Lync Server 2013: Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch XMPP-Verbundbenutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control XMPP federated user access
ms:assetid: 0fe0ff75-e52a-4e3e-923a-64f6412ac4e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552446(v=OCS.15)
ms:contentKeyID: 48679557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7cc0eec0dc1371e27834dda69b25a32b9346ab5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535222"
---
# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a>Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch XMPP-Verbundbenutzer in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Dies ist eine vorläufige Dokumentation und kann jederzeit geändert werden. Leere Themen wurden als Platzhalter hinzugefügt.

Beim Konfigurieren von Richtlinien für die Unterstützung von XMPP-Verbundpartnern (extensible Messaging and Presence Protocol) gelten die Richtlinien für Benutzer von XMPP-Partnerverbunddomänen, aber nicht für Benutzer von SIP (Session Initiation Protocol)-Chatdienstanbietern (z. B. Windows Live) oder von SIP-Partnerverbunddomänen. Sie konfigurieren einen **XMPP-Verbund Partner** für jede XMPP-Verbunddomäne, die Sie Ihren Benutzern erlauben möchten, Kontakte hinzuzufügen und mit Ihnen zu kommunizieren. XMPP-Verbundpartner-Richtlinien sind nur in einem einzigen Bereich verfügbar, obwohl Sie nicht als globale Richtlinie definiert sind und als globale Richtlinie fungieren. Um eine globale, Standort-oder Benutzerrichtlinie für XMPP-Verbundpartner zu definieren, konfigurieren Sie den Richtlinienbereich, indem Sie zuerst die Richtlinie für den externen Zugriff für den von Ihnen benötigten Bereich erstellen und konfigurieren. Ausführliche Informationen zu den Typen von Richtlinien, die Sie für den externen Zugriff und den Partnerverbund konfigurieren können, finden Sie unter [Managing Federation and External Access to lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in der Betriebsdokumentation.

<div>


> [!NOTE]  
> Alle Richtlinien für den <STRONG>Verbund und den externen Zugriff</STRONG> werden über die in-Band-Überstellung angewendet. Die Richtlinien, die für den Benutzer gelten, zu einem Standort gehören oder Global im Bereich sind, werden dem Client während der Anmeldung mitgeteilt. Sie können Richtlinien konfigurieren, um den Zugriff auf XMPP-Verbundpartner zu steuern, selbst wenn Sie den XMPP-Verbund für Ihre Organisation nicht aktiviert haben. Die von Ihnen konfigurierten Richtlinien werden jedoch nur wirksam, wenn Sie einen XMPP-Partnerverbund bereitgestellt, aktiviert und für Ihre Organisation konfiguriert haben. Ausführliche Informationen zum Bereitstellen und Konfigurieren des XMPP-partnerverbunds finden Sie unter <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Configuring SIP Federation, XMPP Federation und Public Instant Messaging in lync Server 2013</A> in der Bereitstellungsdokumentation. Wenn Sie außerdem eine Benutzerrichtlinie in der Richtlinie für den externen Zugriff zur Steuerung von XMPP-Verbundpartnern angeben, gilt die Richtlinie nur für Benutzer, die für lync Server 2013 aktiviert und für die Verwendung der Richtlinie konfiguriert sind.



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a>So bearbeiten Sie eine globale Richtlinie für XMPP-Verbundpartner

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Richtlinie für den externen Zugriff**.

4.  Führen Sie auf der Seite **Richtlinie für den externen Zugriff** folgende Schritte für die globale Richtlinie aus:

5.  Klicken Sie auf die globale Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf Details anzeigen.

6.  Geben Sie eine Beschreibung für die globale Richtlinie an (optional).

7.  Wählen Sie **Kommunikation mit Partnerbenutzern aktivieren** aus.

8.  Wählen Sie **Kommunikation mit XMPP-Partnerverbundbenutzern aktivieren** aus.

9.  Klicken Sie auf **Commit** , um die Änderungen an der globalen Richtlinie zu speichern.

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a>So erstellen Sie eine Standort-oder Benutzerrichtlinie für XMPP-Verbundpartner

1.  Klicken Sie auf **neu**, und klicken Sie dann auf **Website Richtlinie** oder **Benutzerrichtlinie**. Klicken Sie im Dialogfeld **Standort auswählen** in der Liste auf den entsprechenden Standort, und klicken Sie dann auf **OK**.

2.  Geben Sie eine Beschreibung für die Standortrichtlinie an (optional).

3.  Wählen Sie in der Standort-oder Benutzerrichtlinie die Option **Kommunikation mit Verbundbenutzern aktivieren**aus.

4.  Wählen Sie **Kommunikation mit XMPP-Partnerverbundbenutzern aktivieren** aus.

5.  Klicken Sie auf **Commit ausführen**, um Ihre Änderungen am Standort oder an der Benutzerrichtlinie zu speichern.

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a>So bearbeiten Sie eine vorhandene Richtlinie für XMPP-Verbundpartner

1.  Zum Ändern einer vorhandenen Richtlinie wählen Sie in der Liste die entsprechende Richtlinie aus, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

2.  Ändern oder aktualisieren Sie die Beschreibung für die Richtlinie (optional).

3.  Aktivieren oder deaktivieren Sie die Option **Kommunikation mit Verbundbenutzern aktivieren**.

4.  Wählen Sie oder deaktivieren Sie die Option **Kommunikation mit XMPP-Verbundbenutzern aktivieren**.

5.  Klicken Sie auf **Commit** , um die Änderungen an der Richtlinie zu speichern.

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>So bearbeiten Sie eine vorhandene Richtlinie für XMPP-Verbundpartner mithilfe von Windows PowerShell

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Geben Sie im lync Server-Verwaltungsshell Folgendes ein:
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Ein Beispielbefehl, mit dem die globale Richtlinie für den Verbundbenutzer Zugriff auf true (aktiviert) und XMPP-Domänenzugriff auf true festgelegt wird (aktiviert):
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a>So erstellen Sie eine Standort-oder Benutzerrichtlinie für XMPP-Verbundpartner mit Windows PowerShell

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Geben Sie im lync Server-Verwaltungsshell Folgendes ein:
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Ein Beispielbefehl, mit dem eine Standortrichtlinie für den Standort "Redmond" für den Verbundbenutzer Zugriff auf den aktivierten und den XMPP-Domänenzugriff auf "aktiviert" festgelegt wird:
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>So löschen Sie eine vorhandene Richtlinie für XMPP-Verbundpartner mithilfe von Windows PowerShell

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Geben Sie im lync Server-Verwaltungsshell Folgendes ein:
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    Ein Beispielbefehl, mit dem eine Benutzerrichtlinie gelöscht wird:
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  Ein Beispielbefehl, mit dem die globale Richtlinie auf Standardwerte zurückgesetzt wird:
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Zuweisen einer Richtlinie für den externen Benutzer Zugriff zu einem lync-aktivierten Benutzer in lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[Aktivieren oder Deaktivieren der Verbund-und Public Chat-Konnektivität in lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[Verwalten von XMPP-Verbundpartnern in lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Gruppe-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

