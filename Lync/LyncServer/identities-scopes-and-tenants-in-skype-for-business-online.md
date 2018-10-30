---
title: Identitäten, Bereiche und Mandanten
TOCTitle: Identitäten, Bereiche und Mandanten
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56269299
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Identitäten, Bereiche und Mandanten

 

_**Letztes Änderungsdatum des Themas:** 2015-06-22_

Viele der Windows PowerShell-Cmdlets, die für die Verwaltung von Skype for Business Online verwendet werden, setzen voraus, dass Sie im genaue Details zu dem Element angeben, das Sie zu verwalten versuchen. Wenn Sie beispielsweise das Cmdlet [Set-CsUserAcp](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsUserAcp) ausführen, müssen Sie angeben, welchen Benutzer Sie verwalten möchten. Das ergibt Sinn. Erst wenn Sie im Cmdlet speziell angeben, welches Benutzerkonto Sie verwalten möchten, kann das Cmdlet **Set-CsUserAcp** wissen, für welchen Benutzer die Audiokonferenzinformationen geändert werden sollen. Aus diesem Grund müssen Sie jedes Mal, wenn Sie das Cmdlet **Set-CsUserAcp** ausführen, den Parameter **Identity** gefolgt von der Identität des zu ändernden Benutzerkontos angeben:

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

Wenn sich der Begriff *Identität* immer auf die Identität eines Benutzerkontos beziehen würde, gäbe es wohl kaum Verwirrung. Wenn Sie es mit Personen (Benutzern, Kontakten usw.) zu tun haben, beziehen sich die Identitäten auf die einzelnen Benutzer als solche. Allerdings können auch andere Elemente außer Benutzerkonten ebenfalls über eine Identität verfügen. Wenn Sie es mit den Komponenten des Skype for Business Online-Diensts zu tun haben, d.h. mit Richtlinien, Konfigurationseinstellungen usw., erhält der Begriff "Identität" eine etwas andere Bedeutung. Betrachten wir beispielsweise einmal den folgenden Befehl:

    Get-CsMeetingConfiguration -Identity "global"

In diesem Fall bezieht sich **Identity "global"** auf den Bereich der Besprechungskonfigurationseinstellungen. Der Begriff *Bereich* wird in Skype for Business Online (und in Lync Server) verwendet, um Verwaltungsbereiche zu bezeichnen. Standardmäßig weisen Richtlinien und Einstellungen immer einen globalen Bereich auf. Bei der Ersteinrichtung Ihres Skype for Business Online-Kontos wird Ihnen standardmäßig eine Auflistung an globalen Richtlinien und Einstellungen zugewiesen – globale Besprechungskonfigurationseinstellungen, eine globale Richtlinie für den externen Zugriff, ein globaler Wählplan usw.

Diese globalen Richtlinien und Einstellungen wurden mit Microsoft Lync Server 2010 eingeführt, zur Sicherstellung beizutragen, dass alle Benutzer und alle Komponenten immer in irgendeiner Weise verwaltet werden. Das traf in Microsoft Office Communicator 2007 R2 nicht immer zu. Je nachdem, wie Sie auf das System zugegriffen haben, könnten Sie potenziell in einem weitgehend unverwalteten Zustand enden (normalerweise, weil Ihrem Benutzerkonto keine Gruppenrichtlinie zugewiesen werden konnte). In Lync Server und in Skype for Business Online hingegen gibt es nichts, was nicht verwaltet wird, da "anstelle von irgendetwas anderem" immer globale Richtlinien und Einstellungen durchgesetzt werden.

Was bedeutet "anstelle von irgendetwas anderem"? Nun, im Fall von Skype for Business Online ist es möglich, Richtlinie im *Tagbereich* oder dem Verwaltungsbereich zu erstellen. Richtlinien, die im Tagbereich (auch als *benutzerbasierter Bereich* bezeichnet) erstellt werden, haben Vorrang vor Richtlinien, die im globalen Bereich erstellt werden. Anders ausgedrückt, eine benutzerbasierte Richtlinie hat immer Vorrang vor einer globalen Richtlinie. Einmal angenommen, es gibt zwei Richtlinien für den Zugriff von externen Benutzern. Die globale Richtlinie verhindert, dass Benutzer mit Personen kommunizieren, die Konten bei öffentlichen Instant Messaging-Anbietern wie Windows Live haben. Die benutzerbasierte Richtlinie **AllowPublicIMCommunication** gestattet jedoch die Kommunikation mit öffentlichen Instant Messaging-Anbietern.

Nehmen wir weiterhin an, dass es zwei Benutzer gibt, Ken Myer und Pilar Ackerman. Ken Myer wurde die benutzerbasierte Richtlinie zugewiesen. Pilar Ackerman wurde die benutzerbasierte Richtlinie nicht zugewiesen, d. h. sie wird von der globalen Richtlinie für den externen Zugriff verwaltet. Die folgende Tabelle zeigt, welcher Benutzer (wenn überhaupt) mit öffentlichen Instant Messaging-Anbietern kommunizieren kann:


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
<td><p>Globale Richtlinieneinstellung für öffentliche Instant Messaging-Anbieter</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="even">
<td><p>Benutzerbasierte Richtlinieneinstellung für öffentliche Instant Messaging-Anbieter</p></td>
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


Wie Sie sehen, ist es Ken Myer gestattet, mit öffentlichen Instant Messaging-Anbietern zu kommunizieren, da die Einstellungen in der ihm zugewiesenen benutzerbasierten Richtlinie die Einstellungen in der globalen Richtlinie außer Kraft setzen. Pilar Ackerman kann nicht mit öffentlichen Instant Messaging-Anbietern kommunizieren, da sie von der globalen Richtlinie verwaltet wird, die diese Kommunikation verbietet.

Benutzerbasierte Richtlinien müssen vom Office 365-Support für Sie erstellt werden. Nachdem die Richtlinien erstellt wurden, können Sie Sie mit dem geeigneten Cmdlet **Grant-Cs** (z. B. [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)) den jeweiligen Benutzern zuweisen. Benutzerbasierte Richtlinien sind leicht zu erkennen, da die Richtlinie **Identity** immer mit dem Tag-**Präfix** beginnt. Ein Beispiel:

    Identity : tag:AllowPublicIMCommunication


> [!NOTE]
> Das Tag-<STRONG>Präfix</STRONG> stammt aus der Frühzeit der Entwicklung von Lync Server 2010. In dieser Zeit wurden benutzerbasierte Richtlinien als <EM>Tagrichtlinien</EM> bezeichnet und anhand des Tag-<STRONG>Präfix</STRONG> identifiziert. Diese Richtlinien werden heute treffender als <EM>benutzerbasierte Richtlinien</EM> bezeichnet, und der Tagbereich wird – ebenfalls treffender – als <EM>benutzerbasierter Bereich</EM> bezeichnet. Aus technischen Gründen wurde das Tag-<STRONG>Präfix</STRONG> jedoch nie geändert.



Ein anderer Schlüsselbegriff, auf den Sie bei der Arbeit mit Skype for Business Online und Windows PowerShell immer wieder stoßen werden, ist *Mandant*. Wenn Sie ein neues Skype for Business Online-Konto einrichten, wird der neuen Bereitstellung eine Mandanten-ID-Nummer zugewiesen, bei der es sich um einen GUID (Globally Unique Identifier) ähnlich dem folgenden handelt:

    bf19b7db-6960-41e5-a139-2aa373474354

Einige der Skype for Business Online-Cmdlets setzen voraus, dass Sie die Mandanten-ID bei jeder Ausführung des Cmdlets eingeben. Sie müssen die Mandanten-ID sogar eingeben, wenn Sie sich nur bei einem Mandanten angemeldet haben und auch nur einen Mandanten besitzen. Glücklicherweise müssen Sie sich die Mandanten-ID nicht merken. Sie können die Mandanten-ID jederzeit mit dem folgenden Windows PowerShell-Befehl abrufen:

    Get-CsTenant | Select-Object TenantId

Natürlich ist es noch nicht damit getan, Fakten wie den Unterschied zwischen dem globalen Bereich und dem benutzerdefinierten Bereich (Tagbereich) zu kennen. Es ist auch wichtig zu wissen, wann (und sogar ob) Sie diese Bereiche verwenden können. Das gleiche gilt für Identitäten und den Mandantenparameter. Unter den folgenden Themen wird beschrieben, wie unterschiedlicheSkype for Business Online-Cmdlets Identitäten, Bereiche und den Mandantenparameter verwenden:

  - [Cmdlets, die nur den globalen Gültigkeitsbereich verwenden](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [Cmdlets, die den globalen Gültigkeitsbereich und den Tagbereich verwenden](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [Cmdlets, in denen eine Benutzeridentität verwendet wird](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [Cmdlets, die eine Benutzeridentität und den Tagbereich verwenden](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [Cmdlets, in denen der Parameter "Tenant" verwendet wird](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [Cmdlets, in denen eine Konferenzanbieteridentität verwendet wird](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [Cmdlets, die keinen Bereich oder keine Identität verwenden](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

