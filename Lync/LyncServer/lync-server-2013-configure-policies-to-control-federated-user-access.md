---
title: 'Lync Server 2013: Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control federated user access
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1aeb1b29637fd3f4a8add770470069e8b4a6eb8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-federated-user-access-in-lync-server-2013"></a>Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-02-05_

Wenn Sie Richtlinien für die Unterstützung der Kommunikation mit Verbundpartnern konfigurieren, gelten die Richtlinien für Benutzer von Verbunddomänen. Sie können eine oder mehrere Richtlinien für den externen Benutzer Zugriff konfigurieren, um zu steuern, ob Benutzer von Verbunddomänen mit ihren lync Server 2013-Benutzern zusammenarbeiten können. Zum Steuern des Zugriffs von Verbundbenutzern können Sie Richtlinien auf globaler, Website-und Benutzerebene konfigurieren. Lync Server-Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden. Die Priorität der lync Server-Richtlinie lautet: Benutzerrichtlinien (der meiste Einfluss) überschreibt eine Website Richtlinie, und eine Website Richtlinie überschreibt eine globale Richtlinie (geringster Einfluss). Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.

<div>


> [!NOTE]  
> Sie können Richtlinien zum Steuern des Zugriffs von Verbundbenutzern konfigurieren, auch wenn Sie den Verbund für Ihre Organisation nicht aktiviert haben. Die von Ihnen konfigurierten Richtlinien gelten jedoch nur, wenn der Verbund für Ihre Organisation aktiviert ist. Details zum Aktivieren von Föderation finden Sie unter <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013</A> in der Bereitstellungsdokumentation oder in der Betriebsdokumentation. Wenn Sie eine Benutzerrichtlinie zum Steuern des Zugriffs von Verbundbenutzern angeben, gilt die Richtlinie zudem nur für Benutzer, die für lync Server 2013 aktiviert und für die Verwendung der Richtlinie konfiguriert sind.



</div>

<div>

## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>So konfigurieren Sie eine Richtlinie zur Unterstützung des Zugriffs durch Benutzer von Verbunddomänen

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie dann auf **Richtlinie für den externen Zugriff**.

4.  Führen Sie auf der Seite " **externe Zugriffsrichtlinie** " eine der folgenden Aktionen aus:
    
      - Klicken Sie zum Konfigurieren der globalen Richtlinie zur Unterstützung des Zugriffs von Verbundbenutzern auf die globale Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.
    
      - Klicken Sie zum Erstellen einer neuen Website Richtlinie auf **neu**, und klicken Sie dann auf **Website Richtlinie**. Klicken Sie unter **Website auswählen**auf die entsprechende Website in der Liste, und klicken Sie dann auf **OK**.
    
      - Klicken Sie zum Erstellen einer neuen Benutzerrichtlinie auf **neu**, und klicken Sie dann auf **Benutzerrichtlinie**. Erstellen Sie in der **neuen Richtlinie für den externen Zugriff**im Feld **Name** einen eindeutigen Namen, der angibt, was die Benutzerrichtlinie umfasst (beispielsweise **EnableFederatedUsers** für eine Benutzerrichtlinie, die die Kommunikation für Verbunddomänen Benutzer aktiviert).
    
      - Wenn Sie eine vorhandene Richtlinie ändern möchten, klicken Sie auf die entsprechende in der Tabelle aufgelistete Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  Optional Wenn Sie eine Beschreibung hinzufügen oder bearbeiten möchten, geben Sie die Informationen für die Richtlinie unter **Beschreibung**an.

6.  Führen Sie einen der folgenden Schritte aus:
    
      - Wenn Sie den Verbundbenutzer Zugriff für die Richtlinie aktivieren möchten, aktivieren Sie das Kontrollkästchen **Kommunikation mit verbundenen Benutzern aktivieren** .
    
      - Wenn Sie den Verbundbenutzer Zugriff für die Richtlinie deaktivieren möchten, deaktivieren Sie das Kontrollkästchen **Kommunikation mit verbundenen Benutzern aktivieren** .

7.  Klicken Sie auf **Commit ausführen**.

Zum Aktivieren des Zugriffs auf den Verbundbenutzer müssen Sie auch die Unterstützung für den Verbund in Ihrer Organisation aktivieren. Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen in lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).

Wenn es sich um eine Benutzerrichtlinie handelt, müssen Sie die Richtlinie auch auf Benutzer anwenden, die in der Lage sein sollen, mit Verbundbenutzern zusammenzuarbeiten. Ausführliche Informationen finden Sie unter [Zuweisen einer externen Benutzerzugriffs Richtlinie zu einem lync-aktivierten Benutzer in lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).

</div>

<div>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>So konfigurieren Sie eine vorhandene Richtlinie mithilfe von Windows PowerShell zur Unterstützung des Zugriffs durch Benutzer von Verbunddomänen

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Geben Sie in der lync Server-Verwaltungsshell Folgendes ein:
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    Ein Beispielbefehl, der die globale Richtlinie für den Verbundbenutzer Zugriff auf Enabled, XMPP-Domänenzugriff auf aktiviert, Remote Benutzer Zugriff auf aktiviert, Zugriff durch öffentliche Anbieter auf aktiviert und die Möglichkeit zur Verwendung von Audio und Video für öffentliche Anbieter, die es unterstützen, festlegen soll:
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    
    <div>
    

    > [!TIP]  
    > Der Parameter "EnablePublicCloudAudioVideoAccess" hat in der lync Server-Systemsteuerung keine entsprechende Auswahl.

    
    </div>

</div>

<div>

## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>So erstellen Sie eine neue Richtlinie mithilfe von Windows PowerShell zur Unterstützung des Zugriffs durch Benutzer von Verbunddomänen

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Geben Sie in der lync Server-Verwaltungsshell Folgendes ein:
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    Ein Beispiel für das Erstellen einer neuen Website Richtlinie:
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

</div>

<div>

## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>So löschen oder setzen Sie eine Richtlinie mithilfe von Windows PowerShell zurück, um den Zugriff durch Benutzer von Verbunddomänen zu unterstützen

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Geben Sie in der lync Server-Verwaltungsshell Folgendes ein:
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    Ein Beispiel für das Zurücksetzen der globalen Richtlinie (für die globale Richtlinie kann nur die Einstellung entfernt werden. Die Richtlinie kann nicht gelöscht werden):
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    Um eine Website Richtlinie zu entfernen, geben Sie Folgendes ein:
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    Löscht die Website Richtlinie Redmond. Zum Löschen einer Benutzerrichtlinie mit dem Namen UserEAPPolicy geben Sie Folgendes ein:
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer zu einem für Lync aktivierten Benutzer in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  


[Verwalten von SIP-Partnerdomänen für eine Organisation in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Verwalten von SIP-Partnerverbundanbietern für eine Organisation in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
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

