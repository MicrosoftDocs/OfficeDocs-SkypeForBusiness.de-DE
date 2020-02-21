---
title: 'Lync Server 2013: Konfigurieren von Active Directory Verbunddiensten (AD FS 2.0)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Active Directory Federation Services (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308561(v=OCS.15)
ms:contentKeyID: 54973682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9daaec9cbe32f031c7ee99731b1d7c7c9ec10ac1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195718"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a>Konfigurieren von Active Directory Verbunddiensten (AD FS 2.0) für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-07-03_

Im folgenden Abschnitt wird beschrieben, wie Sie Active Directory Verbunddienste (AD FS 2.0) zur Unterstützung der mehrstufigen Authentifizierung konfigurieren. Informationen zum Installieren von AD FS 2.0 finden Sie unter AD FS 2.0 Schritt-für-Schritt und Anleitungen unter [https://go.microsoft.com/fwlink/p/?LinkId=313374](https://go.microsoft.com/fwlink/p/?linkid=313374).

<div class="">


> [!NOTE]  
> Verwenden Sie beim Installieren von AD FS 2.0 nicht den Windows Server-Manager, um die Active Directory Rolle "Verbunddienste" hinzuzufügen. Laden Sie stattdessen das RTW-Paket für Active Directory Verbunddienste 2,0 unter <A href="https://go.microsoft.com/fwlink/p/?linkid=313375">https://go.microsoft.com/fwlink/p/?LinkId=313375</A>herunter, und installieren Sie es.



</div>

<div>


**So konfigurieren Sie AD FS für die zweistufige Authentifizierung**

1.  Melden Sie sich mit einem Domänenadministratorkonto beim AD FS 2.0 Computer an.

2.  Starten Sie Windows PowerShell.

3.  Führen Sie in der Windows PowerShell Befehlszeile den folgenden Befehl aus:
    ```powershell
    add-pssnapin Microsoft.Adfs.PowerShell
    ```
4.  Erstellen Sie eine Partnerschaft mit jedem lync Server 2013 mit kumulativen Updates für lync Server 2013: July 2013 Director, Enterprise-Pool und Standard Edition-Server, die für die passive Authentifizierung aktiviert werden, indem Sie den folgenden Befehl ausführen, und ersetzen Sie den für Ihre Bereitstellung spezifischer Servername:
    ```powershell
    Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  Starten Sie im Menü Verwaltungs Tools die AD FS 2.0 Verwaltungskonsole.

6.  Erweitern Sie Vertrauensstellungen der vertrauenden **Seite**der **Vertrauensstellung** \> .

7.  Stellen Sie sicher, dass für Ihre lync Server 2013 eine neue Vertrauensstellung mit kumulierten Updates für lync Server 2013 erstellt wurde: July 2013 Enterprise-Pool oder Standard Edition-Server.

8.  Erstellen und Zuweisen einer Ausstellungs Autorisierungsregel für die Vertrauensstellung der vertrauenden Seite mithilfe Windows PowerShell, indem Sie die folgenden Befehle ausführen:
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  Erstellen und Zuweisen einer Ausstellungs Transformationsregel für die Vertrauensstellung der vertrauenden Seite mithilfe Windows PowerShell, indem Sie die folgenden Befehle ausführen:
    
       ```powershell
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. Klicken Sie in der AD FS 2.0-Verwaltungskonsole mit der rechten Maustaste auf die Vertrauensstellung der vertrauenden Seite, und wählen Sie **Anspruchsregeln bearbeiten**aus.

11. Wählen Sie die Registerkarte **Ausstellungs Autorisierungsregeln** aus, und stellen Sie sicher, dass die neue Autorisierungsregel erfolgreich erstellt wurde.

12. Wählen Sie die Registerkarte **ausstellungstransformationsregeln** aus, und stellen Sie sicher, dass die neue Transformationsregel erfolgreich erstellt wurde.

</div>

</div>

<span> </span>

</div>

</div>

</div>

