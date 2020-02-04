---
title: 'Lync Server 2013: Löschen eines Kontaktobjekts für einen öffentlichen Bereich'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a common area phone Contact object
ms:assetid: f4c139dc-f07c-4c75-9345-e291aea41173
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994087(v=OCS.15)
ms:contentKeyID: 51803999
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a3088150c882a5ebca99318f7c85ddbddddc333
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a>Löschen eines Kontaktobjekts für einen öffentlichen Bereich in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-20_

Möglicherweise möchten Sie das Kontaktobjekt löschen, das mit einem Telefon im öffentlichen Bereich verknüpft ist. Wenn Sie beispielsweise das Telefon aus einer Mitarbeiter Lounge entfernen, müssen Sie nicht über ein Kontaktobjekt verfügen, das diesem Telefon zugeordnet ist. Das Cmdlet **Remove-CsCommonAreaPhone** bietet eine Möglichkeit zum Löschen von Telefonkonten im allgemeinen Bereich. Wenn Sie dieses Cmdlet ausführen, wird das Telefon aus der Liste der von **Get-CsCommonAreaPhone**zurückgegebenen Telefone des öffentlichen Bereichs gelöscht. Darüber hinaus wird das dem Telefon zugeordnete Kontaktobjekt aus den Active Directory-Domänendiensten gelöscht.

Verwenden **Sie Remove-CsCommonAreaPhone** , um ein Telefon im öffentlichen Bereich oder alle Telefone mit gemeinsamem Bereich zu entfernen, die ein gemeinsames Element aufweisen, beispielsweise einen Anzeigenamen oder eine Landes-und Ortsvorwahl. Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a>Entfernen eines angegebenen öffentlichen Bereichs Telefons

  - Mit dem folgenden Befehl wird das Telefon des öffentlichen Bereichs mit der SIP-Adresse SIP:mainlobby@litwareinc.com entfernt:
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a>Entfernen von Telefonen im allgemeinen Bereich auf der Grundlage Ihres Anzeigenamens

  - Mit diesem Befehl werden alle Telefone im öffentlichen Bereich entfernt, wobei der Anzeigename den Zeichenfolgenwert "Building 14" enthält:
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a>Entfernen von Festnetz-Telefonen auf der Grundlage ihrer Landes-und Ortsvorwahl

  - Mit diesem Befehl werden alle Telefone im öffentlichen Bereich für die Vereinigten Staaten (Landesvorwahl 1) und die Ortsvorwahl 425 entfernt:
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) .

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

