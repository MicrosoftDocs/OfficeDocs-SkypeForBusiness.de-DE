---
title: 'Lync Server 2013: Erstellen oder Ändern eines Kontaktobjekts für ein Telefon mit öffentlichen Bereichen'
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
ms.openlocfilehash: 699fd4413e071a9377369a383c9fd379a3451c6a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151857"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a>Erstellen oder Ändern eines Kontaktobjekts für ein Telefon mit öffentlichen Bereichen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-20_

Verwenden Sie das **New-CsCommonAreaPhone-** Cmdlet, um Active Directory-Domänendienste Kontaktobjekte für alle Telefone im öffentlichen Bereich zu erstellen. Mit diesem Cmdlet können Sie entweder neue Kontaktobjekte für Telefone in öffentlichen Bereichen erstellen oder vorhandene Kontaktobjekte einem neuen Telefon im öffentlichen Bereich zuordnen. Verwenden Sie das Cmdlet "CsCommonAreaPhone", um die Eigenschaften der Contact **-** Objekte zu ändern, die mit Telefonen in öffentlichen Bereichen verknüpft sind. Mit den optionalen Parametern für " **CsCommonAreaPhone** " können Sie Elemente ändern, beispielsweise den Anzeigenamen des Active Directory Kontakts oder den dem Telefon zugeordneten-URI (Uniform Resource Identifier) und das Konto für die Verwendung mit lync Server aktivieren und deaktivieren. Ausführliche Informationen zu allen verfügbaren Änderungen finden Sie im Abschnitt Parameters unter [Festlegen von CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone). Ausführliche Informationen zu **New-CsCommonAreaPhone** -Parametern finden Sie unter [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).

Sie können diese beiden Cmdlets sowohl in der lync Server 2013-Verwaltungsshell als auch in einer Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a>Erstellen eines Kontaktobjekts für ein Telefon mit öffentlichen Bereichen

  - Verwenden Sie das **New-CsCommonAreaPhone-** Cmdlet, um ein neues Kontaktobjekt für eine öffentliche Telefonanlage zu erstellen. Sie müssen mindestens die folgenden Informationen angeben, wenn Sie ein Contact-Objekt erstellen:
    
      - **LineUri**: die Telefonnummer, die dem Telefon im öffentlichen Bereich zugewiesen ist. Beachten Sie, dass Sie beim Angeben der Telefonnummer das E. 164-Format verwenden müssen.
    
      - **RegistrarPool**: der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Registrierungsstellen Pools, der als Host für das Contact-Objekt verwendet wird.
    
      - **OU**: DN (Distinguished Name) des Active Directory Containers, in dem das Contact-Objekt erstellt wird.
    
    Außerdem wird empfohlen, einen Active Directory-Domänendienste Anzeigenamen anzugeben. Andernfalls müssen Sie eine GUID verwenden, um die Telefon Identität anzugeben. Zum Beispiel:
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a>Ändern eines Kontaktobjekts für ein Telefon mit öffentlichen Bereichen

  - Um die Eigenschaften eines vorhandenen Telefons für gemeinsame Bereiche zu ändern, verwenden Sie das Cmdlet " **Sets-CsCommonAreaPhone** ". Mit dem folgenden Befehl wird beispielsweise die SIP-Adresse für das Telefon für öffentliche Bereiche mit der DisplayName-Lobby konfiguriert:
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

Ausführliche Informationen finden Sie in den Hilfethemen für das [New-CsCommonAreaPhone-](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) Cmdlet und das Cmdlet "Set [-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) ".

</div>

</div>

<span> </span>

</div>

</div>

</div>

