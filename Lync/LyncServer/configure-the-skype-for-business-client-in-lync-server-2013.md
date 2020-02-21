---
title: Konfigurieren des Skype for Business Clients in lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the client experience
ms:assetid: 61e783f1-24f4-430b-ae52-c76a4d206dc7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn954919(v=OCS.15)
ms:contentKeyID: 65227958
ms.date: 09/18/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b89457c35bc9c9c0150b84ab34f4103776206ad
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180778"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-client-experience-with-skype-for-business"></a>Konfigurieren der Clientumgebung mit Skype for Business

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2015-09-17_

**Zusammenfassung:** In diesem Thema wird beschrieben, wie Sie die Clientumgebung für Skype for Business Clientbenutzer in einer lync Server 2013 Umgebung konfigurieren. Sie können die Clienterfahrung nur konfigurieren, wenn Sie lync Server 2013 mit dem kumulativen Update vom Dezember 2014 (5.0.8308.857) oder höher installieren. Informationen zum Aktualisieren von lync Server 2013 finden Sie unter [Updates für lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532651).

Skype for Business bietet eine neue Benutzeroberfläche, die auf der Skype Consumer-Produkterfahrung basiert. Zusätzlich zu allen Funktionen von lync bietet Skype for Business neue Features mit vereinfachten Steuerelementen und vertrauten Symbolen. Ausführliche Informationen zu den neuen Clientfunktionen finden Sie unter [lync ist jetzt Skype for Business--siehe What es New](https://go.microsoft.com/fwlink/?linkid=529022).

Lync Server 2013 unterstützt die neue Skype for Business-Clientumgebung sowie die lync-Clientumgebung. Als Administrator können Sie die bevorzugte Clientumgebung für Ihre Benutzer auswählen. Beispielsweise können Sie die lync-Clientumgebung bereitstellen, bis Benutzer in Ihrer Organisation in der neuen Skype for Business Erfahrung voll ausgebildet sind. Oder wenn Sie noch nicht alle Benutzer auf Skype for Business Server 2015 aktualisiert haben, möchten Sie möglicherweise, dass alle Benutzer die gleiche Clienterfahrung haben, bis alle auf den neuen Server aktualisiert wurden.

<div>


> [!IMPORTANT]  
> Wenn Ihre Organisation sowohl Skype for Business Server 2015 als auch lync Server 2013 bereitgestellt hat, unterscheidet sich die standardmäßige Clientumgebung je nach Server Versionen und Benutzeroberflächeneinstellungen. Wenn Benutzer Skype for Business zum ersten Mal starten, wird immer die Skype for Business-Benutzeroberfläche angezeigt, auch wenn Sie die lync-Benutzeroberfläche ausgewählt haben. Nach einigen Minuten werden die Benutzer aufgefordert, in den lync-Modus zu wechseln. Weitere Informationen finden Sie unter <STRONG>First Launch Client Behavior</STRONG> weiter unten in diesem Thema.



</div>

<div>


> [!NOTE]  
> Die lync 2013 Clienterfahrung ist keine Option für Skype for Business 2016-Clientversionen. Bevor Sie versuchen, ihre Clientumgebung für die Verwendung des lync 2013 Clients zu konfigurieren, überprüfen Sie die Client Version, um sicherzustellen, dass Sie nicht mit der Nummer 16 beginnt; Beispiel: 16. x.x.x.



</div>

<div>

## <a name="configure-the-client-experience"></a>Konfigurieren der Clientumgebung

Sie können die Clientumgebung angeben, in der die Benutzer in Ihrer Organisation angezeigt werden, indem Sie das Cmdlet " **CSClientPolicy** " mit dem Parameter "EnableSkypeUI" verwenden. Mit dem folgenden Befehl wird die Skype for Business Clientumgebung für alle Benutzer in Ihrer Organisation ausgewählt, die von der globalen Richtlinie betroffen sind (denken Sie daran, dass Standort-oder benutzerspezifische Richtlinien die globale Richtlinie außer Kraft setzen):

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

Der nächste Befehl wählt die lync-Clientumgebung für alle Benutzer in Ihrer Organisation aus, die von der globalen Richtlinie betroffen sind:

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

Der nächste Befehl wählt die Skype for Business Clientumgebung für alle Benutzer innerhalb des Standorts "Redmond" aus:

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

Wenn Sie die Clientumgebung für bestimmte Benutzer in Ihrer Organisation konfigurieren möchten, können Sie mithilfe des Cmdlets **New-CsClientPolicy** eine neue Benutzerrichtlinie erstellen und dann die Richtlinie bestimmten Benutzern zuweisen, indem Sie das Cmdlet **Grant-CsClientPolicy** verwenden.

Mit dem folgenden Befehl wird beispielsweise eine neue Clientrichtlinie salesclientui "erstellt, mit der die Skype for Business Clientumgebung ausgewählt wird:

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

Der nächste Befehl ordnet die Richtlinie, salesclientui ", allen Mitgliedern der Vertriebsabteilung zu:

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a>Clientverhalten zuerst starten

Wenn Benutzer Skype for Business zum ersten Mal starten, wird Ihnen standardmäßig immer die Skype for Business Benutzeroberfläche angezeigt, auch wenn Sie die lync-Clientumgebung ausgewählt haben, indem Sie den Wert des Parameters EnableSkypeUI auf $false wie zuvor beschrieben festlegen. . Nach einigen Minuten werden die Benutzer aufgefordert, in den lync-Modus zu wechseln.

Wenn Sie die lync-Benutzeroberfläche anzeigen möchten, wenn Benutzer den Skype for Business-Client zum ersten Mal starten, führen Sie die folgenden Schritte aus, bevor der Client zum ersten Mal nach dem Aktualisieren gestartet wird:

1.  Stellen Sie sicher, dass `EnableSkypeUI` der Wert von auf $false in der Richtlinie festgelegt ist, die Sie wie zuvor beschrieben verwenden.

2.  Aktualisieren Sie die Systemregistrierung auf dem Computer des Benutzers. Dies sollten Sie tun, bevor Benutzer den Skype for Business-Client zum ersten Mal starten, und Sie sollten dies nur einmal tun. Informationen zum Erstellen eines Gruppenrichtlinienobjekts zum Aktualisieren der Registrierung auf einem Computer mit Domänenbeitritt finden Sie im Abschnitt weiter unten in diesem Thema.
    
    Erstellen Sie ** \[im\_HKEY\_aktuellen\\Benutzer\\Software\\-\\Microsoft\] Office-lync** -Schlüssel einen neuen **binären** Wert.
    
    Der **Wertname** muss **EnableSkypeUI**sein, und die **Wertdaten** müssen auf **00 00 00 00**festgelegt werden.
    
    Der Schlüssel sollte wie folgt aussehen:
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

Die lync-Benutzeroberfläche wird nun angezeigt, wenn Benutzer den Skype for Business-Client zum ersten Mal starten.

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Steuern der Anzeige des Lernprogramms für Begrüßungsbildschirm

Wenn Benutzer den Skype for Business-Client öffnen, wird standardmäßig ein Begrüßungsbildschirm angezeigt, der *7 schnelle Tipps enthält, nach denen die meisten Personen Fragen*. Sie können die Anzeige des Begrüßungsbildschirms deaktivieren, aber dennoch Benutzern den Zugriff auf das Lernprogramm gestatten, indem Sie den folgenden Registrierungswert auf dem Clientcomputer hinzufügen:

Erstellen Sie ** \[in\_der\_HKEY\\-\\aktuellen\\Benutzer\\Software\\Microsoft\] Office 15,0 lync** Key einen neuen **DWORD-Wert (32-Bit)**. Der **Wertname** muss **IsBasicTutorialSeenByUser**sein, und die **Wertdaten** müssen auf **1**festgelegt werden.

Der Schlüssel sollte wie folgt aussehen:

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a>Deaktivieren des Client-Lernprogramms

Wenn Sie nicht möchten, dass Ihre Benutzer auf das Lernprogramm zugreifen können, können Sie das Client Lernprogramm mit dem folgenden Registrierungswert deaktivieren:

Erstellen Sie ** \[in\_der\_HKEY\\-\\aktuellen\\Benutzer\\Software\\Microsoft\] Office 15,0 lync** Key einen neuen **DWORD-Wert (32-Bit)**. Der **Wertname** muss **TutorialFeatureEnabled**sein, und die **Wertdaten** müssen auf **0**festgelegt werden.

    "TutorialFeatureEnabled"=dword:00000000

Sie können das Lernprogramm wieder aktivieren, indem Sie den **Wert Data** auf **1**festlegen.

</div>

</div>

<div>

## <a name="default-client-experiences"></a>Standard Client-Benutzeroberflächen

Wenn Ihre Organisation sowohl Skype for Business Server 2015 als auch lync Server bereitgestellt wird, unterscheidet sich die Clientumgebung je nach Server Version und der Skype-Benutzeroberflächeneinstellung. In der folgenden Tabelle ist die anfängliche Clienterfahrung basierend auf der Server Version und der Benutzeroberflächeneinstellung dargestellt:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Server Version</p></th>
<th><p>EnableSkypeUI-Einstellung</p></th>
<th><p>Client Erfahrung</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype for Business Server 2015</p></td>
<td><p>Standard</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Skype for Business Server 2015</p></td>
<td><p>Wahr</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="odd">
<td><p>Skype for Business Server 2015</p></td>
<td><p>False</p></td>
<td><p>Der Benutzer hat aufgefordert, in den lync-Modus zu wechseln (Benutzer kann später zu Skype for Business wechseln, wenn Sie die Benutzeroberflächeneinstellung in $true ändern)</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 oder lync Server 2013 (mit korrekten Patches)</p></td>
<td><p>Standard</p></td>
<td><p>Der Benutzer hat aufgefordert, in den lync-Modus zu wechseln (Benutzer kann später zu Skype for Business wechseln, wenn Sie die Benutzeroberflächeneinstellung in $true ändern)</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 oder lync Server 2013 (mit korrekten Patches)</p></td>
<td><p>Wahr</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 oder lync Server 2013 (mit korrekten Patches)</p></td>
<td><p>False</p></td>
<td><p>Der Benutzer hat aufgefordert, in den lync-Modus zu wechseln (Benutzer kann später zu Skype for Business wechseln, wenn Sie die Benutzeroberflächeneinstellung in $true ändern)</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 oder lync Server 2013 (ohne Patches)</p></td>
<td><p>Standard</p></td>
<td><p>Benutzer wurde aufgefordert, zur lync-Clientumgebung zu wechseln (Benutzer kann später nicht zu Skype for Business wechseln)</p></td>
</tr>
</tbody>
</table>


Die folgende Tabelle zeigt die Clientumgebung, wenn der Administrator die anfängliche Einstellung für die Skype-Benutzeroberfläche ändert:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Server Version</p></th>
<th><p>Einstellung der Skype-Benutzeroberfläche</p></th>
<th><p>Client-Benutzeroberfläche = lync</p></th>
<th><p>Client UI = Skype for Business</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype for Business Server 2015</p></td>
<td><p>Wahr</p></td>
<td><p>Der Benutzer hat aufgefordert, zu Skype for Business zu wechseln</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Skype for Business Server 2015</p></td>
<td><p>False</p></td>
<td><p>Lync-Benutzeroberfläche</p></td>
<td><p>Benutzer aufgefordert, zur lync-Benutzeroberfläche zu wechseln</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 oder lync Server 2013 (mit korrekten Patches)</p></td>
<td><p>Wahr</p></td>
<td><p>Der Benutzer hat aufgefordert, zu Skype for Business zu wechseln</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 oder lync Server 2013 (mit korrekten Patches)</p></td>
<td><p>False</p></td>
<td><p>Lync-Benutzeroberfläche</p></td>
<td><p>Benutzer aufgefordert, zur lync-Benutzeroberfläche zu wechseln</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 oder lync Server 2013 (ohne Patches)</p></td>
<td><p>Standard</p></td>
<td><p>Lync-Modus (kann nicht zu Skype for Business wechseln)</p></td>
<td><p>Lync-Benutzeroberfläche (kann nicht zu Skype for Business wechseln)</p></td>
</tr>
</tbody>
</table>


Die für die Verwaltung der Konfiguration des Skype for Business Clients erforderlichen Patch-Versionen sind:

  - Lync Server 2010-Februar 2015 Kumulatives Update (4.0.7577.710) für lync Server 2010. Weitere Informationen finden Sie unter [Updates für lync Server 2010](https://go.microsoft.com/fwlink/p/?linkid=532771)

  - Lync Server 2013-Dezember 2014 Kumulatives Update (5.0.8308.857) für lync Server 2013. Weitere Informationen finden Sie unter [Updates für lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532772).

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Erstellen eines Gruppenrichtlinienobjekts zum Ändern der Registrierung auf einem Computer, der einer Domäne angehört

Das Registrierungsupdate zum Anzeigen der lync-Clientumgebung, wenn ein Benutzer das erste Mal den Skype for Business-Client startet, sollte nur einmal ausgeführt werden. Wenn Sie ein Gruppenrichtlinienobjekt (Group Policy Object, GPO) zum Aktualisieren der Registrierung verwenden, müssen Sie das Objekt definieren, um einen neuen Wert zu erstellen, statt die Wertdaten zu aktualisieren. Wenn das Gruppenrichtlinienobjekt angewendet wird und der neue Wert nicht vorhanden ist, wird es vom GPO erstellt und die Wertdaten auf 0 festgelegt.

Im folgenden Verfahren wird beschrieben, wie Sie die Registrierung so ändern, dass die lync-Clientumgebung angezeigt wird, wenn ein Benutzer das Skype for Business zum ersten Mal startet. Sie können dieses Verfahren auch verwenden, um die Registrierung zu aktualisieren, um das Lernprogramm für Begrüßungsbildschirm wie zuvor beschrieben zu deaktivieren.

**So erstellen Sie das GPO**

1.  Starten Sie die **Gruppenrichtlinien-Verwaltungskonsole**.
    
    Informationen zur Verwendung der Gruppenrichtlinien-Verwaltungskonsole finden Sie unter [Gruppenrichtlinien-Verwaltungskonsole](https://go.microsoft.com/fwlink/?linkid=532759).

2.  Klicken Sie mit der rechten Maustaste auf den Knoten **Gruppenrichtlinienobjekte** , und wählen Sie im Menü **neu** aus.

3.  Geben Sie im Dialogfeld **Neues Gruppenrichtlinienobjekt** einen Namen für das GPO ein, beispielsweise **MakeLyncDefaultUI**, und klicken Sie dann auf **OK**.

4.  Klicken Sie mit der rechten Maustaste auf das neue GPO, das Sie soeben erstellt haben, und wählen Sie dann im Menü **Bearbeiten** aus.

5.  Erweitern Sie im **Gruppenrichtlinien-Verwaltungs-Editor**die Option **Benutzerkonfiguration**, erweitern Sie **Einstellungen**, erweitern Sie **Windows-Einstellungen**, und wählen Sie dann den **Registrierungs** Knoten aus.

6.  Klicken Sie mit der rechten Maustaste auf den **Registrierungs** Knoten, und wählen Sie dann **Neues** \> **Registrierungselement**aus.

7.  Aktualisieren Sie im Dialogfeld **neue Registrierungseigenschaften** Folgendes:
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Feld</th>
    <th>Auszuwählender oder einzugebender Wert</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Aktion</strong></p></td>
    <td><p><strong>Create</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Struktur</strong></p></td>
    <td><p>HKEY_CURRENT_USER</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Schlüsselpfad</strong></p></td>
    <td><p>Software\Microsoft\Office\Lync</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Wertname</strong></p></td>
    <td><p>EnableSkypeUI</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Werttyp</strong></p></td>
    <td><p>REG_BINARY</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Value data</strong></p></td>
    <td><p>00000000</p></td>
    </tr>
    </tbody>
    </table>


8.  Klicken Sie auf **OK** , um die Änderungen zu speichern, und schließen Sie dann das GPO.

Als nächstes müssen Sie das erstellte GPO mit der Gruppe von Benutzern verknüpfen, denen Sie die Richtlinie zuweisen möchten, beispielsweise einer Organisationseinheit.

**So verwenden Sie das GPO zum Zuweisen der Richtlinie**

1.  Klicken Sie in der Gruppenrichtlinien-Verwaltungskonsole mit der rechten Maustaste auf die Organisationseinheit, der Sie die Richtlinie zuweisen möchten, und wählen Sie dann **Verknüpfung mit einem vorhandenen GPO**aus.

2.  Wählen Sie im Dialogfeld **GPO auswählen** das erstellte GPO aus, und wählen Sie dann **OK**aus.

3.  Öffnen Sie auf dem Computer des Zielbenutzers eine Eingabeaufforderung, und geben Sie den folgenden Befehl ein:
    
    **gpupdate/Target: Benutzer**
    
    Die Meldung "Richtlinie wird aktualisiert..." wird angezeigt, während das Gruppenrichtlinienobjekt angewendet wird. Wenn der Vorgang abgeschlossen ist, wird die Meldung "Benutzerrichtlinien Aktualisierung wurde erfolgreich abgeschlossen" angezeigt.

4.  Geben Sie an der Eingabeaufforderung den folgenden Befehl ein:
    
    **gpresult/r**
    
    Sie sollten "zugewiesene Gruppenrichtlinienobjekte" mit dem Namen des erstellten Gruppenrichtlinienobjekts sehen, das unten angezeigt wird.

Sie können auch überprüfen, ob das GPO die Registrierung auf dem Computer eines Benutzers erfolgreich aktualisiert hat, indem Sie die Registrierung untersuchen. Öffnen Sie den ** \[Registrierungs-Editor, und\_navigieren\_Sie\\zum\\HKEY\\aktuellen\\Benutzer\] Software-Microsoft Office lync** -Schlüssel. Wenn das GPO die Registrierung erfolgreich aktualisiert hat, wird der Wert "EnableSkypeUI" mit dem Wert "0" angezeigt.

</div>

</div>

<span> </span>

</div>

</div>

</div>

