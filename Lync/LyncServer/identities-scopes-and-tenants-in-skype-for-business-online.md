---
title: Identitäten, Bereiche und Mandanten in Skype for Business Online
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Identities, scopes, and tenants
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56558817
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b08c459f64a4655ebb4dc670255645f985452aa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722975"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a>Identitäten, Bereiche und Mandanten in Skype for Business Online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Für viele der Windows PowerShell-Cmdlets, die für die Verwaltung von Skype for Business Online verwendet werden, müssen Sie sehr genau über das Element verfügen, das Sie verwalten möchten. Wenn Sie beispielsweise das Cmdlet " [Satz-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) " ausführen, müssen Sie angeben, welchen Benutzer Sie verwalten möchten. Das macht Sinn. Wenn Sie dem Cmdlet nicht ausdrücklich mitteilen, welches Benutzerkonto verwaltet werden soll, hat das Cmdlet " **Satz-CsUserAcp** " keine Ahnung, welche Audio-Konferenz Informationen des Benutzers geändert werden sollten. Aus diesem Grund müssen Sie jedes Mal, wenn Sie das Cmdlet " **Satz-CsUserAcp** " ausführen, den Parameter Identity und dann die Identität des zu ändernden Benutzerkontos einbeziehen:

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

Wenn der Ausdruck *Identity* immer auf die Identität eines Benutzerkontos Bezug genommen hat, gibt es nur wenige Ursachen für Verwirrung. Wenn Sie mit Personen (Benutzern, Kontakten usw.) zu tun haben, verweisen Identitäten auf die einzelnen Benutzer selbst. Elemente, die keine Benutzerkonten sind, weisen aber auch Identitäten auf. Wenn es sich um Komponenten des Skype for Business Online-Diensts (Richtlinien, Konfigurationseinstellungen usw.) handelt, bedeutet der Ausdruck Identität etwas anderes. Sehen Sie sich beispielsweise diesen Befehl an:

    Get-CsMeetingConfiguration -Identity "global"

In diesem Fall bezieht sich die Identität "Global" auf den Bereich der Konfigurationseinstellungen für Besprechungen. *Scope* ist ein Ausdruck, der in Skype for Business Online (und in lync Server) verwendet wird, um die Bereiche der Verwaltung festzulegen. Standardmäßig verfügen Richtlinien und Einstellungen immer über einen globalen Bereich. Wenn Sie Ihr Skype for Business Online-Konto zum ersten Mal einrichten, verfügen Sie standardmäßig über eine Sammlung globaler Richtlinien und Einstellungen – globale Besprechungs Konfigurationseinstellungen, eine globale Richtlinie für den externen Zugriff, einen globalen Wählplan usw.

Diese globalen Richtlinien und Einstellungen wurden in Microsoft lync Server 2010 eingeführt, um sicherzustellen, dass alle Benutzer und alle Komponenten immer in irgendeiner Weise verwaltet werden. Dies war in Microsoft Office Communicator 2007 R2 nicht unbedingt der Fall. Je nachdem, wie Sie auf das System zugegriffen haben, könnten Sie möglicherweise in einem weitgehend unverwalteten Zustand enden (in der Regel, weil Gruppenrichtlinien nicht auf Ihr Benutzerkonto angewendet werden konnten). Im Gegensatz dazu wird in lync Server und in Skype for Business Online nichts jemals unverwaltet gelassen. Der Grund dafür ist, dass globale Richtlinien und Einstellungen immer erzwungen werden, anstatt irgendetwas anderes zu tun.

Was meinen wir mit "anstelle von irgendetwas anderem"? Nun, im Fall von Skype for Business Online ist es möglich, Richtlinien im *Bereich "Tag*" oder "Bereich der Verwaltung" zu erstellen. Richtlinien, die mit dem Tag-Bereich (auch als benutzerspezifischer *Bereich*bezeichnet) erstellt wurden, haben Vorrang vor im globalen Bereich erstellten Richtlinien. Anders ausgedrückt: eine benutzerspezifische Richtlinie hat immer Vorrang vor einer globalen Richtlinie. So können Sie beispielsweise zwei Richtlinien für den externen Benutzer Zugriff haben. Die globale Richtlinie verbietet Benutzern, mit Personen zu kommunizieren, die über Konten für öffentliche Instant Messaging-Anbieter (im) wie Windows Live verfügen. Die benutzerspezifische Richtlinie AllowPublicIMCommunication ermöglicht die Kommunikation mit öffentlichen Chat Anbietern.

Sie haben möglicherweise auch zwei Benutzer: Ken Myers und Pilar Ackerman. Ken Myers wurde die Richtlinie pro Benutzer zugewiesen. Pilar Ackerman wurde keine Richtlinie pro Benutzer zugewiesen; Das heißt, dass Sie von der globalen Richtlinie für den externen Zugriff verwaltet wird. Die folgende Tabelle zeigt, welche Benutzer (falls vorhanden) mit öffentlichen Chat Anbietern kommunizieren können:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Richtlinieneinstellungen</th>
<th>Ken Myer</th>
<th>Pilar Ackerman</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Globale Richtlinieneinstellung für öffentliche Chat Anbieter</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="even">
<td><p>Benutzerspezifische Richtlinieneinstellung für öffentliche Chat Anbieter</p></td>
<td><p>Ja</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="odd">
<td><p>Der Benutzer kann mit öffentlichen Chat Anbietern kommunizieren</p></td>
<td><p>Ja</p></td>
<td><p>Nein</p></td>
</tr>
</tbody>
</table>


Wie Sie sehen können, ist es Ken Myers gestattet, mit öffentlichen Chat Dienstanbietern zu kommunizieren. Der Grund hierfür ist, dass die Einstellungen in der ihm zugewiesenen Benutzerrichtlinie die Einstellungen in der globalen Richtlinie außer Kraft setzen. Pilar Ackerman kann nicht mit öffentlichen Chat Anbietern kommunizieren. Dies liegt daran, dass Sie von der globalen Richtlinie verwaltet wird und die globale Richtlinie diese Kommunikation untersagt.

Richtlinien für einzelne Benutzer müssen vom Office 365-Support für Sie erstellt werden. Nachdem die Richtlinien erstellt wurden, können Sie Sie den Benutzern mithilfe des entsprechenden **Grant-CS-** Cmdlets zuweisen (beispielsweise [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)). Richtlinien für einzelne Benutzer sind einfach zu erkennen, da die Richtlinien Identität immer mit dem **Tagpräfix beginnt.** Beispiel:

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> Das Tagpräfix <STRONG>geht auf</STRONG> die frühen Entwicklungstage von lync Server 2010 zurück. In diesen Tagen wurden Richtlinien für einzelne Benutzer als <EM>Transponder Richtlinien</EM> bezeichnet und durch <STRONG>das Tagpräfix identifiziert.</STRONG> Diese Richtlinien werden jetzt genauer als benutzerspezifische <EM>Richtlinien</EM>bezeichnet, und der Transponder Bereich wird genauer als benutzerspezifischer <EM>Bereich</EM>bezeichnet. Aus technischen <STRONG>Gründen wurde das Tagpräfix jedoch</STRONG> nie geändert.



</div>

Ein weiterer wichtiger Ausdruck, der bei der Arbeit mit Skype for Business Online und Windows PowerShell verwendet wird, ist *Mandant*. Wenn Sie ein Skype for Business Online-Konto einrichten, wird Ihrer neuen Bereitstellung eine Mandanten-ID zugewiesen, bei der es sich um eine GUID (Globally Unique Identifier) handelt, die der folgenden ähnelt:

    bf19b7db-6960-41e5-a139-2aa373474354

Bei einigen der Skype for Business Online-Cmdlets müssen Sie die Mandanten-ID eingeben, wenn Sie das Cmdlet ausführen. Sie müssen die Mandanten-ID eingeben, selbst wenn Sie sich angemeldet haben und nur einen Mandanten haben. Glücklicherweise müssen Sie die Mandanten-ID nicht auswendig lernen. Sie können Ihre Mandanten-ID jederzeit abrufen, indem Sie den folgenden Windows PowerShell-Befehl ausführen:

    Get-CsTenant | Select-Object TenantId

Das Erkennen von Dingen wie dem Unterschied zwischen dem globalen Bereich und dem Bereich pro Benutzer (oder dem Tag-Bereich) ist natürlich nur die halbe Schlacht. Darüber hinaus ist es wichtig zu wissen, wann (oder sogar ob) Sie diese Bereiche verwenden können. Das gleiche gilt für Identitäten und den Mandanten Parameter. In den folgenden Themen wird beschrieben, wie die verschiedenen Skype for Business Online-Cmdlets Identitäten, Bereiche und den Mandanten Parameter verwenden:

  - [Cmdlets in Skype for Business Online, die nur den globalen Bereich verwenden](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [Cmdlets in Skype for Business Online, die den globalen Bereich und den Transponder Bereich verwenden](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [Cmdlets in Skype for Business Online, die eine Benutzeridentität verwenden](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [Cmdlets in Skype for Business Online, die eine Benutzeridentität und den Transponder Bereich verwenden](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [Cmdlets in Skype for Business Online, die den Mandanten Parameter verwenden](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [Cmdlets in Skype for Business Online, die eine Konferenzanbieter Identität verwenden](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [Cmdlets in Skype for Business Online, die keinen Bereich oder keine Identität verwenden](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

