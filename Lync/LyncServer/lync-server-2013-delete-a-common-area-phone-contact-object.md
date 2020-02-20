---
title: 'Lync Server 2013: Löschen eines Kontaktobjekts für eine Telefonanlage für gemeinsame Bereiche'
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
ms.openlocfilehash: c77d9c220502abbd4275af337142927786be9be3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a>Löschen eines Kontaktobjekts für einen öffentlichen Bereich in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-20_

Möglicherweise möchten Sie das Kontaktobjekt löschen, das einem Telefon im öffentlichen Bereich zugeordnet ist. Wenn Sie beispielsweise das Telefon aus einer Mitarbeiter Lounge entfernen, muss diesem Telefon kein Kontaktobjekt zugeordnet sein. Das Cmdlet **Remove-CsCommonAreaPhone** bietet Ihnen die Möglichkeit, Telefonkonten für gemeinsame Bereiche zu löschen. Wenn Sie dieses Cmdlet ausführen, wird das Telefon aus der Liste der Telefone in öffentlichen Bereichen gelöscht, die von **Get-CsCommonAreaPhone**zurückgegeben werden. Darüber hinaus wird das dem Telefon zugeordnete Kontaktobjekt aus Active Directory-Domänendienste gelöscht.

Verwenden **Sie Remove-CsCommonAreaPhone** , um ein Telefon für gemeinsame Bereiche oder alle Telefone für gemeinsame Bereiche mit einem gemeinsamen Element wie Anzeigename oder Land-und Ortsvorwahl zu entfernen. Sie können dieses Cmdlet entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a>Entfernen eines angegebenen Telefons für gemeinsame Bereiche

  - Mit dem folgenden Befehl wird das Telefon für öffentliche Bereiche mit der SIP-Adresse SIP:mainlobby@litwareinc.com entfernt:
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a>Entfernen von Telefonen in öffentlichen Bereichen basierend auf Ihrem Anzeigenamen

  - Mit diesem Befehl werden alle Telefone im öffentlichen Bereich entfernt, wobei der Anzeigename den Zeichenfolgenwert "Building 14" enthält:
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a>Entfernen von Telefonen in öffentlichen Bereichen basierend auf ihren Landes-und Ortsvorwahl

  - Mit diesem Befehl werden alle Telefone für gemeinsame Bereiche für die Vereinigten Staaten (Ländercode 1) und die Vorwahl 425 entfernt:
    
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

