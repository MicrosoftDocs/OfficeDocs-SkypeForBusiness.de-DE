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
ms.openlocfilehash: 9dd2008984707f1f8e76b7e61074d5303c0d0819
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a>Identitäten, Bereiche und Mandanten in Skype for Business Online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2015-03-09_

Viele der Windows PowerShell-Cmdlets, die zum Verwalten von Skype for Business Online verwendet werden, erfordern eine sehr genaue über das Element, das Sie verwalten möchten. Wenn Sie beispielsweise das Cmdlet " [CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) " ausführen, müssen Sie angeben, welche Benutzer Sie verwalten möchten. Das ist aus dem folgenden Grund sinnvoll: Die w:lvl-Elemente werden nur von Entwicklern verwendet, und nullbasierte Indizes sind für Entwickler leichter zu handhaben. Wenn Sie dem Cmdlet nicht explizit mitteilen, welches Benutzerkonto verwaltet werden soll, hat das Cmdlet " **CsUserAcp** " keine Ahnung, welche Audiokonferenzinformationen des Benutzers geändert werden sollten. Aus diesem Grund müssen Sie bei jedem Ausführen des Cmdlets " **CsUserAcp** " den Parameter "Identity" angeben, gefolgt von der Identität des zu ändernden Benutzerkontos:

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

Wenn der Begriff *Identity* immer auf die Identität eines Benutzerkontos Bezug genommen wird, gibt es nur wenig Anlass zur Verwirrung. Wenn Sie mit Personen (Benutzern, Kontakten usw.) zu tun haben, bezieht sich die Identität auf die einzelnen Benutzer selbst. Andere Elemente als Benutzerkonten weisen jedoch auch Identitäten auf. Wenn Sie sich mit Komponenten des Skype for Business Online Diensts – Richtlinien, Konfigurationseinstellungen usw. – befassen, bedeutet der Ausdruck "Identity" etwas anderes. Verwenden Sie beispielsweise diesen Befehl:

    Get-CsMeetingConfiguration -Identity "global"

In diesem Fall bezieht sich die Identität "Global" auf den Bereich der Besprechungs Konfigurationseinstellungen. *Scope* ist ein Begriff, der in Skype for Business Online (und in lync Server) zum Festlegen von Verwaltungsbereichen verwendet wird. Standardmäßig haben Richtlinien und Einstellungen immer einen globalen Bereich. Beim ersten Einrichten Ihres Skype for Business Online-Kontos haben Sie standardmäßig eine Sammlung globaler Richtlinien und Einstellungen – globale Besprechungs Konfigurationseinstellungen, eine globale Richtlinie für den externen Zugriff, einen globalen Wählplan usw.

Diese globalen Richtlinien und Einstellungen wurden in Microsoft lync Server 2010 eingeführt, um sicherzustellen, dass alle Benutzer und alle Komponenten immer in irgendeiner Weise verwaltet werden können. Dies war in Microsoft Office Communicator 2007 R2 nicht unbedingt der Fall. Je nachdem, wie Sie auf das System zugegriffen haben, könnten Sie möglicherweise in einem weitgehend nicht verwalteten Zustand enden (in der Regel, da Gruppenrichtlinien nicht auf Ihr Benutzerkonto angewendet werden konnten). Im Gegensatz dazu wird in lync Server und in Skype for Business Online nichts mehr verwaltet. Dies liegt daran, dass an Stelle von nichts anderem globale Richtlinien und Einstellungen immer erzwungen werden.

Was meinen wir mit "anstelle von irgendetwas anderem"? Nun, im Fall von Skype for Business Online ist es möglich, Richtlinien im *Tag-Bereich*oder im Bereich der Verwaltung zu erstellen. Auf dem Tag-Bereich (auch bekannt als benutzerbezogener *Bereich*) erstellte Richtlinien haben Vorrang vor Richtlinien, die auf globaler Ebene erstellt werden. Mit anderen Worten: eine benutzerspezifische Richtlinie hat immer Vorrang vor einer globalen Richtlinie. Beispielsweise können Sie zwei Richtlinien für den Zugriff durch externe Benutzer haben. Die globale Richtlinie untersagt Benutzern die Kommunikation mit Personen, die über Konten für öffentliche Chat Anbieter (Instant Messaging) wie Windows Live verfügen. Die benutzerspezifische Richtlinie, AllowPublicIMCommunication, ermöglicht die Kommunikation mit öffentlichen Instant Messaging-Anbietern.

Möglicherweise haben Sie auch zwei Benutzer: Ken Myers und Pilar Ackerman. Ken Myers wurde die benutzerspezifische Richtlinie zugewiesen. Pilar Ackerman wurde keine benutzerspezifische Richtlinie zugewiesen. Dies bedeutet, dass Sie von der globalen Richtlinie für den externen Zugriff verwaltet wird. In der folgenden Tabelle wird gezeigt, welcher Benutzer (falls vorhanden) mit öffentlichen Instant Messaging-Anbietern kommunizieren kann:


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
<td><p>Benutzer kann mit öffentlichen Instant Messaging-Anbietern kommunizieren</p></td>
<td><p>Ja</p></td>
<td><p>Nein</p></td>
</tr>
</tbody>
</table>


Wie Sie sehen können, kann Ken Myers mit öffentlichen Instant Messaging-Anbietern kommunizieren. Dies liegt daran, dass die Einstellungen in der benutzerbezogenen Richtlinie, die ihm zugewiesen ist, die Einstellungen in der globalen Richtlinie außer Kraft setzen. Pilar Ackerman kann nicht mit öffentlichen Instant Messaging-Anbietern kommunizieren. Dies liegt daran, dass Sie von der globalen Richtlinie verwaltet wird und die globale Richtlinie solche Kommunikationen verbietet.

Benutzerspezifische Richtlinien müssen für Sie durch Office 365 Support erstellt werden. Nachdem die Richtlinien erstellt wurden, können Sie Sie Benutzern mithilfe des entsprechenden Cmdlets **Grant-CS** zuweisen (beispielsweise [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)). Benutzerspezifische Richtlinien sind leicht zu identifizieren, da die Richtlinien Identität immer mit **dem Tagpräfix beginnt.** Zum Beispiel:

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> Das Tagpräfix wird auf die frühen Entwicklungstage von lync Server 2010 <STRONG>zurück datiert.</STRONG> In diesen Tagen wurden benutzerspezifische Richtlinien als <EM>Tag-Richtlinien</EM> bezeichnet und durch <STRONG>das Tagpräfix identifiziert.</STRONG> Diese Richtlinien werden nun genauer als benutzerspezifische <EM>Richtlinien</EM>bezeichnet, und der Transponder Bereich wird genauer als benutzerbezogener <EM>Bereich</EM>bezeichnet. Aus technischen <STRONG>Gründen wurde das Tagpräfix jedoch</STRONG> nie geändert.



</div>

Ein weiterer Schlüsselbegriff, der beim Arbeiten mit Skype for Business Online und Windows PowerShell verwendet wird, ist " *Mandant*". Wenn Sie ein Skype for Business Online-Konto einrichten, wird Ihrer neuen Bereitstellung eine Mandanten-ID zugewiesen, bei der es sich um eine GUID (Globally Unique Identifier) wie die folgende handelt:

    bf19b7db-6960-41e5-a139-2aa373474354

Bei einigen der Skype for Business Online-Cmdlets müssen Sie die Mandanten-ID eingeben, wenn Sie das Cmdlet ausführen. Sie müssen die Mandanten-ID auch dann eingeben, wenn Sie sich angemeldet haben und nur einen Mandanten haben. Glücklicherweise müssen Sie die Mandanten-ID nicht merken. Sie können Ihre Mandanten-ID jederzeit abrufen, indem Sie den folgenden Windows PowerShell-Befehl ausführen:

    Get-CsTenant | Select-Object TenantId

Selbstverständlich ist das Erkennen von Dingen wie dem Unterschied zwischen dem globalen und dem benutzerbezogenen Bereich (oder dem Tag-Bereich) nur die Hälfte der Schlacht. Es ist auch wichtig zu wissen, wann (oder sogar wenn) Sie diese Bereiche verwenden können. Gleiches gilt für Identitäten und den Parameter Mandanten. In den folgenden Themen wird beschrieben, wie die verschiedenen Skype for Business Online-Cmdlets Identitäten, Bereiche und den Parameter Mandanten verwenden:

  - [Cmdlets in Skype for Business Online, die nur den globalen Bereich verwenden](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [Cmdlets in Skype for Business Online, die den globalen Bereich und den Tag-Bereich verwenden](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [Cmdlets in Skype for Business Online, die eine Benutzeridentität verwenden](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [Cmdlets in Skype for Business Online, die eine Benutzeridentität und den Tag-Bereich verwenden](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [Cmdlets in Skype for Business Online, die den Parameter "Mandant" verwenden](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [Cmdlets in Skype for Business Online, die eine Konferenzanbieter Identität verwenden](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [Cmdlets in Skype for Business Online, die keinen Bereich oder eine Identität verwenden](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

