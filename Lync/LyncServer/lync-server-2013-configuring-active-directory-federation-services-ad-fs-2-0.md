---
title: 'Lync Server 2013: Konfigurieren der Active Directory-Verbunddienste (AD FS 2,0)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Active Directory Federation Services (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308561(v=OCS.15)
ms:contentKeyID: 54973682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 924f9c1b6e7fe64186eeee6a34364417d497866b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a>Konfigurieren der Active Directory-Verbunddienste (AD FS 2,0) für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-07-03_

Im folgenden Abschnitt wird beschrieben, wie Active Directory-Partnerverbunddienste (AD FS 2.0) konfiguriert werden muss, damit die mehrstufige Authentifizierung unterstützt wird. Informationen zum Installieren von AD FS 2,0 finden Sie unter Schritt-für-Schritt-Anleitungen zu AD FS 2,0 und Anleitungen unter [http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374).

<div class="">


> [!NOTE]  
> Wenn Sie AD FS 2.0 installieren, dürfen Sie nicht den Windows Server Manager verwenden, um die Active Directory-Partnerverbunddienste-Rolle hinzuzufügen. Laden Sie stattdessen das 2,0-RTW-Paket für Active Directory Federation Services <A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>unter herunter, und installieren Sie es.



</div>

<div>


**So konfigurieren Sie AD FS für die zweistufige Authentifizierung**

1.  Melden Sie sich beim AD FS 2.0-Computer über ein Domänenadministratorkonto an.

2.  Starten Sie Windows PowerShell.

3.  Führen Sie aus der Windows PowerShell-Befehlszeile den folgenden Befehl aus:
    
        add-pssnapin Microsoft.Adfs.PowerShell

4.  Einrichten einer Partnerschaft mit jedem lync Server 2013 mit kumulativen Updates für lync Server 2013: Juli 2013 Director, Enterprise-Pool und Standard Edition-Server, die für die passive Authentifizierung aktiviert werden, indem Sie den folgenden Befehl ausführen, wobei die für Ihre Bereitstellung spezifischer Servername:
    
        Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  Starten Sie aus dem Menü „Verwaltung“ die AD FS 2.0-Verwaltungskonsole.

6.  Erweitern von Vertrauensstellungen für **vertrauenswürdige Beziehungen** \> ****.

7.  Überprüfen Sie, ob eine neue Vertrauensstellung für Ihren lync Server 2013 mit kumulativen Updates für lync Server 2013: Juli 2013 Enterprise-Pool oder Standard Edition-Server erstellt wurde.

8.  Erstellen Sie eine Ausstellungsautorisierungsregel für Ihre Vertrauensstellung der vertrauenden Seite und weisen Sie diese Regel zu. Führen Sie dazu über Windows PowerShell die folgenden Befehle aus:
    
       ```
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  Erstellen Sie eine Ausstellungstransformationsregel für Ihre Vertrauensstellung der vertrauenden Seite und weisen Sie diese Regel zu. Führen Sie dazu über Windows PowerShell die folgenden Befehle aus:
    
       ```
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. Klicken Sie in der AD FS 2.0-Verwaltungskonsole mit der rechten Maustaste auf Ihre Vertrauensstellung der vertrauenden Seite und wählen Sie **Anspruchsregeln bearbeiten** aus.

11. Wählen Sie die Registerkarte **Ausstellungsautorisierungsregeln** aus und vergewissern Sie sich, dass die neue Autorisierungsregel erfolgreich erstellt wurde.

12. Wählen Sie die Registerkarte **Ausstellungstransformationsregeln** aus und vergewissern Sie sich, dass die neue Transformationsregel erfolgreich erstellt wurde.

</div>

</div>

<span> </span>

</div>

</div>

</div>

