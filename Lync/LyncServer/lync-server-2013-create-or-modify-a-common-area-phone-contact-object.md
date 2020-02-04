---
title: 'Lync Server 2013: Erstellen oder Ändern eines Telefon Kontaktobjekts in einem gemeinsamen Bereich'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a common area phone Contact object
ms:assetid: eec33ad1-e4f2-49b2-91d6-d5a9d2e1714b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994083(v=OCS.15)
ms:contentKeyID: 51803995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e9e7ddf1a4911b9afb3428531911223f62ea723
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758109"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a>Erstellen oder Ändern eines Telefon Kontaktobjekts in einem gemeinsamen Bereich in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-20_

Verwenden Sie das Cmdlet **New-CsCommonAreaPhone** , um Kontaktobjekte für Active Directory-Domänendienste für alle Ihre Telefone im allgemeinen Bereich zu erstellen. Dieses Cmdlet kann entweder neue Kontaktobjekte für die Verwendung mit öffentlichen Telefonen erstellen, oder es kann vorhandene Kontaktobjekte mit einem neuen Telefon im öffentlichen Bereich verknüpfen. Wenn Sie die Eigenschaften der Kontaktobjekte ändern möchten, die für Telefone im allgemeinen Bereich zugeordnet sind, verwenden Sie das Cmdlet " **Satz-CsCommonAreaPhone** ". Optionale Parameter für "CsCommonAreaPhone" ermöglichen Ihnen, Elemente wie den Active Directory **-** Anzeigenamen des Kontakts oder den dem Telefon zugeordneten Uniform Resource Identifier (URI) zu ändern und das Konto für die Verwendung mit lync Server zu aktivieren und zu deaktivieren. Ausführliche Informationen zu allen verfügbaren Änderungen finden Sie im Abschnitt Parameter unter [CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone). Ausführliche Informationen zu Parametern für **neue CsCommonAreaPhone** finden Sie unter [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).

Sie können diese beiden Cmdlets entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a>Erstellen eines Telefon Kontaktobjekts für einen öffentlichen Bereich

  - Verwenden Sie das Cmdlet **New-CsCommonAreaPhone** , um ein neues Telefon Kontaktobjekt für einen öffentlichen Bereich zu erstellen. Sie müssen mindestens die folgenden Informationen angeben, wenn Sie ein Kontaktobjekt erstellen:
    
      - **LineUri**: die Telefonnummer, die dem Telefon im öffentlichen Bereich zugewiesen ist. Beachten Sie, dass Sie das E. 164-Format verwenden müssen, wenn Sie die Telefonnummer angeben.
    
      - **RegistrarPool**: der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des registrierungspools, in dem das Kontaktobjekt gehostet wird.
    
      - **OU**: Distinguished Name des Active Directory-Containers, in dem das Kontaktobjekt erstellt wird.
    
    Wir empfehlen außerdem, einen Anzeigenamen für Active Directory-Domänendienste bereitzustellen. Andernfalls müssen Sie die Telefon Identität mithilfe einer GUID angeben. Beispiel:
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a>Ändern eines Telefon Kontaktobjekts für einen öffentlichen Bereich

  - Wenn Sie die Eigenschaften eines vorhandenen öffentlichen Bereichs Telefons ändern möchten, verwenden Sie das Cmdlet " **Satz-CsCommonAreaPhone** ". Mit diesem Befehl wird beispielsweise die SIP-Adresse für das Telefon im öffentlichen Bereich mit der DisplayName-Lobby konfiguriert:
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

Ausführliche Informationen finden Sie in den Hilfethemen zum Cmdlet [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) und dem Cmdlet " [Satz-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) ".

</div>

</div>

<span> </span>

</div>

</div>

</div>

