---
title: Konfigurieren des Skype for Business-Clients in lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the client experience
ms:assetid: 61e783f1-24f4-430b-ae52-c76a4d206dc7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn954919(v=OCS.15)
ms:contentKeyID: 65227958
ms.date: 09/18/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fa863fd1775fbc2a726806f2dd4fff5fed5dbfd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-client-experience-with-skype-for-business"></a>Configure the client experience with Skype for Business

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2015-09-17_

**Zusammenfassung:** In diesem Thema wird beschrieben, wie Sie die Clientumgebung für Skype for Business-Clientbenutzer in einer lync Server 2013-Umgebung konfigurieren. Sie können die Clientumgebung nur konfigurieren, wenn Sie lync Server 2013 mit dem kumulativen Update vom Dezember 2014 (5.0.8308.857) oder höher ausführen. Informationen zum Aktualisieren von lync Server 2013 finden Sie unter [Updates für lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=532651).

Skype for Business bietet eine neue Benutzererfahrung, die auf der Skype Consumer-Produkterfahrung basiert. Neben allen Funktionen von lync bietet Skype for Business neue Funktionen mit vereinfachten Steuerelementen und vertrauten Symbolen. Detaillierte Informationen zur neuen Clientumgebung finden Sie unter [lync ist jetzt Skype for Business – sehen Sie, was es neues](http://go.microsoft.com/fwlink/?linkid=529022)gibt.

Lync Server 2013 unterstützt die neue Skype for Business-Clientumgebung sowie die lync-Clientumgebung. Als Administrator können Sie die bevorzugte Clientumgebung für Ihre Benutzer auswählen. So können Sie beispielsweise die lync-Clientumgebung so lange bereitstellen, bis die Benutzer in Ihrer Organisation in der neuen Skype for Business-Benutzeroberfläche umfassend geschult sind. Wenn Sie noch nicht alle Benutzer auf Skype for Business Server 2015 aktualisiert haben, möchten Sie möglicherweise, dass alle Benutzer die gleiche Clientumgebung haben, bis alle auf den neuen Server aktualisiert wurden.

<div>


> [!IMPORTANT]  
> Wenn in Ihrer Organisation Skype for Business Server 2015 und lync Server 2013 bereitgestellt sind, unterscheidet sich die standardmäßige Clientumgebung je nach Server Versionen und UI-Einstellungen. Wenn Benutzer Skype for Business zum ersten Mal starten, sehen Sie immer die Benutzeroberfläche von Skype for Business – auch wenn Sie die lync-Benutzeroberfläche ausgewählt haben. Nach einigen Minuten werden die Benutzer aufgefordert, in den lync-Modus zu wechseln. Weitere Informationen entnehmen Sie dem <STRONG>Abschnitt zum Clientverhalten beim ersten Start</STRONG>.



</div>

<div>


> [!NOTE]  
> Die lync 2013-Clientumgebung ist keine Option für Skype for Business 2016-Clientversionen. Bevor Sie versuchen, ihre Clientumgebung für die Verwendung des lync 2013-Clients zu konfigurieren, überprüfen Sie die Client Version, um sicherzustellen, dass Sie nicht mit der Zahl 16 beginnt; Beispiel: 16. x.x.x.



</div>

<div>

## <a name="configure-the-client-experience"></a>Configure the client experience

Sie können die Clientumgebung angeben, die die Benutzer in Ihrer Organisation sehen, indem Sie das Cmdlet " **Satz-CSClientPolicy** " mit dem EnableSkypeUI-Parameter verwenden. Mit dem folgenden Befehl wird die Skype for Business-Clientumgebung für alle Benutzer in Ihrer Organisation ausgewählt, die von der globalen Richtlinie betroffen sind (denken Sie daran, dass Website-oder benutzerspezifische Richtlinien die globale Richtlinie außer Kraft setzen):

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

Der nächste Befehl wählt die lync-Clientumgebung für alle Benutzer in Ihrer Organisation aus, die von der globalen Richtlinie betroffen sind:

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

Mit dem folgenden Befehl wird die Skype for Business-Clientumgebung für alle Benutzer auf der Website "Redmond" ausgewählt:

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

Wenn Sie die Clientumgebung für bestimmte Benutzer in Ihrer Organisation konfigurieren möchten, können Sie mithilfe des Cmdlets **New-CsClientPolicy** eine neue Benutzerrichtlinie erstellen und dann die Richtlinie bestimmten Benutzern zuweisen, indem Sie die **Grant-CsClientPolicy** Cmdlet.

Mit dem folgenden Befehl wird beispielsweise eine neue Clientrichtlinie, SalesClientUI, erstellt, die die Skype for Business-Clientumgebung auswählt:

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

Der nächste Befehl weist die Richtlinie „SalesClientUI“ allen Mitgliedern der Verkaufsabteilung zu:

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a>Verhalten beim ersten Start des Clients

Wenn Benutzer Skype for Business zum ersten Mal starten, sehen Sie standardmäßig immer die Benutzeroberfläche von Skype for Business – auch wenn Sie die lync-Clientumgebung ausgewählt haben, indem Sie den Wert des EnableSkypeUI-Parameters auf $false festlegen, wie zuvor beschrieben . Nach einigen Minuten wird der Benutzer aufgefordert, in den Lync-Modus zu wechseln.

Wenn beim ersten Start des Skype for Business-Clients die Lync-Benutzeroberfläche angezeigt werden soll, führen Sie die folgenden Schritte aus, bevor der Client nach der Aktualisierung zum ersten Mal gestartet wird:

1.  Vergewissern Sie sich, dass `EnableSkypeUI` der Wert von in der von Ihnen verwendeten Richtlinie auf $false festgesetzt ist, wie zuvor beschrieben.

2.  Aktualisieren Sie die Systemregistrierung auf dem Computer des Benutzers. Sie sollten diesen Schritt ausführen, bevor der Benutzer den Skype for Business-Client erstmalig startet und Sie sollten diesen Schritt nur einmal ausführen. Informationen zum Erstellen eines GPO (Group Policy Object, Gruppenrichtlinienobjekt) für die Aktualisierung der Systemregistrierung auf einem Computer in einer Domäne finden Sie weiter unten in diesem Thema.
    
    Erstellen Sie ** \[im\_HKEY\_-\\aktuellen\\Benutzer\\Software\\-\] Microsoft Office lync** -Schlüssel einen neuen **Binärwert** .
    
    Der **Wertname** muss **EnableSkypeUI** sein und die **Wertdaten** müssen auf **00 00 00 00** festgelegt sein.
    
    Der Schlüssel sollte wie folgt aussehen:
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

Die Lync-Benutzeroberfläche wird nun angezeigt, wenn Benutzer den Skype for Business-Client zum ersten Mal starten.

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Steuern der Anzeige des Lernprogramms auf der Willkommenseite

Wenn Benutzer den Skype for Business-Client öffnen, besteht das Standardverhalten darin, einen Begrüßungsbildschirm anzuzeigen, der *7 schnelle Tipps enthält, nach denen die meisten Personen Fragen*. Sie können die Anzeige der Willkommensseite ausschalten, Benutzern aber die Möglichkeit geben, dennoch auf das Lernprogramm zuzugreifen, indem Sie den folgenden Registrierungswert auf dem Clientcomputer hinzufügen:

Erstellen Sie ** \[im\_HKEY\_-\\aktuellen\\Benutzer\\Software\\-\\Microsoft\] Office 15,0 lync** -Schlüssel einen neuen **DWORD-Wert (32-Bit)**. Der **Wertname** muss **IsBasicTutorialSeenByUser** sein und die **Wertdaten** müssen auf **1** festgelegt sein.

Der Schlüssel sollte wie folgt aussehen:

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a>Ausschalten des Client-Lernprogramms

Wenn Sie nicht möchten, dass die Benutzer auf das Lernprogramm zugreifen, können Sie das Client-Lernprogramm mit dem folgenden Registrierungswert ausschalten:

Erstellen Sie ** \[im\_HKEY\_-\\aktuellen\\Benutzer\\Software\\-\\Microsoft\] Office 15,0 lync** -Schlüssel einen neuen **DWORD-Wert (32-Bit)**. Der **Wertname** muss **TutorialFeatureEnabled** sein und die **Wertdaten** müssen auf **0** festgelegt sein.

    "TutorialFeatureEnabled"=dword:00000000

Sie können das Lernprogramm wieder aktivieren, indem Sie die **Wertdaten** auf **1** festlegen.

</div>

</div>

<div>

## <a name="default-client-experiences"></a>Standard-Client Erlebnisse

Wenn in Ihrer Organisation sowohl Skype for Business Server 2015 als auch lync Server bereitgestellt werden, unterscheidet sich die Clientumgebung je nach Server Version und der Skype-Benutzeroberflächeneinstellung. Die folgende Tabelle zeigt die anfängliche Clientumgebung basierend auf der Serverversion und der Benutzeroberflächeneinstellung:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Serverversion</p></th>
<th><p>EnableSkypeUI-Einstellung</p></th>
<th><p>Client-Erfahrung</p></th>
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
<td><p>True</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="odd">
<td><p>Skype for Business Server 2015</p></td>
<td><p>Falsch</p></td>
<td><p>Der Benutzer hat gebeten, in den lync-Modus zu wechseln (der Benutzer kann später zu Skype for Business wechseln, wenn Sie die UI-Einstellung auf $true ändern)</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 oder lync Server 2013 (mit den richtigen Patches)</p></td>
<td><p>Standard</p></td>
<td><p>Der Benutzer hat gebeten, in den lync-Modus zu wechseln (der Benutzer kann später zu Skype for Business wechseln, wenn Sie die UI-Einstellung auf $true ändern)</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 oder lync Server 2013 (mit den richtigen Patches)</p></td>
<td><p>True</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 oder lync Server 2013 (mit den richtigen Patches)</p></td>
<td><p>Falsch</p></td>
<td><p>Der Benutzer hat gebeten, in den lync-Modus zu wechseln (der Benutzer kann später zu Skype for Business wechseln, wenn Sie die UI-Einstellung auf $true ändern)</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 oder lync Server 2013 (ohne Patches)</p></td>
<td><p>Standard</p></td>
<td><p>Der Benutzer hat gebeten, zur lync-Clientumgebung zu wechseln (der Benutzer kann später nicht mehr zu Skype for Business wechseln)</p></td>
</tr>
</tbody>
</table>


Die nächste Tabelle zeigt die Clientumgebung, wenn der Administrator die anfängliche Einstellung für das Skype-UI-Erlebnis ändert:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Serverversion</p></th>
<th><p>Skype-UI-Einstellung</p></th>
<th><p>Client-UI = lync</p></th>
<th><p>Client-Benutzeroberfläche = Skype for Business</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype for Business Server 2015</p></td>
<td><p>True</p></td>
<td><p>Benutzer hat gebeten, zu Skype for Business zu wechseln</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Skype for Business Server 2015</p></td>
<td><p>Falsch</p></td>
<td><p>Lync-Benutzeroberfläche</p></td>
<td><p>Benutzer hat gebeten, zur lync-Benutzeroberfläche zu wechseln</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 oder lync Server 2013 (mit den richtigen Patches)</p></td>
<td><p>True</p></td>
<td><p>Benutzer hat gebeten, zu Skype for Business zu wechseln</p></td>
<td><p>Skype for Business</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 oder lync Server 2013 (mit den richtigen Patches)</p></td>
<td><p>Falsch</p></td>
<td><p>Lync-Benutzeroberfläche</p></td>
<td><p>Benutzer hat gebeten, zur lync-Benutzeroberfläche zu wechseln</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 oder lync Server 2013 (ohne Patches)</p></td>
<td><p>Standard</p></td>
<td><p>Lync-Modus (kann nicht zu Skype for Business wechseln)</p></td>
<td><p>Lync-Benutzeroberfläche (kann nicht zu Skype for Business wechseln)</p></td>
</tr>
</tbody>
</table>


Die für die Verwaltung der Konfiguration des Skype for Business-Clients erforderlichen Patch-Versionen sind:

  - Lync Server 2010-Februar 2015 Kumulatives Update (4.0.7577.710) für lync Server 2010. Informationen finden Sie unter [Updates für lync Server 2010](http://go.microsoft.com/fwlink/p/?linkid=532771)

  - Lync Server 2013-Dezember 2014 Kumulatives Update (5.0.8308.857) für lync Server 2013. Informationen finden Sie unter [Updates für lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=532772).

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Erstellen eines Gruppenrichtlinienobjekts zum Ändern der Registrierung auf einem Computer in einer Domäne

Die Aktualisierung der Registrierung zur Anzeige der Lync-Clientumgebung beim ersten Start des Skype for Business-Clients durch einen Benutzer sollte nur einmal ausgeführt werden. Wenn Sie für die Aktualisierung der Registrierung ein Gruppenrichtlinienobjekt (GPO) verwenden, müssen Sie das Objekt für die Erstellung eines neuen Werts definieren, anstatt die Wertdaten lediglich zu aktualisieren. Wenn das GPO ohne einen neuen Wert zugewiesen wird, erstellt das GPO einen neuen Wert und setzt die Wertdaten auf 0.

Das nachstehende Verfahren beschreibt, wie die Registrierung geändert werden kann, damit die Lync-Clientumgebung beim ersten Start von Skype for Business auf dem Computer des Benutzers angezeigt wird. Sie haben damit auch die Möglichkeit, die Registrierung für die Deaktivierung des Lernprogramms auf der Willkommensseite zu aktualisieren.

**So erstellen Sie das Gruppenrichtlinienobjekt**

1.  Starten Sie die **Gruppenrichtlinien-Verwaltungskonsole**.
    
    Informationen zur Verwendung der Gruppenrichtlinien-Verwaltungskonsole finden Sie unter [Gruppenrichtlinien-Verwaltungskonsole](http://go.microsoft.com/fwlink/?linkid=532759).

2.  Klicken Sie mit der rechten Maustaste auf den Knoten **Gruppenrichtlinienobjekte** und wählen Sie im Menü **Neu** aus.

3.  Geben Sie im Dialogfeld **Neues Gruppenrichtlinienobjekt** einen Namen für das Gruppenrichtlinienobjekt (z. B. **MakeLyncDefaultUI**) ein und klicken Sie dann auf **OK**.

4.  Klicken Sie mit der rechten Maustaste auf das soeben erstellte neue Gruppenrichtlinienobjekt und wählen Sie dann im Menü **Bearbeiten** aus.

5.  Im **Gruppenrichtlinienverwaltungs-Editor** erweitern Sie **Benutzerkonfiguration**, dann **Einstellungen** und dann **Windows-Einstellungen** und wählen Sie anschließend den Knoten **Registrierung** aus.

6.  Klicken Sie mit der rechten Maustaste auf den **Registrierungs** Knoten, und wählen Sie dann **Neues** \> **Registrierungselement**aus.

7.  Aktualisieren Sie im Dialogfeld **Neue Registrierungseigenschaften** die folgenden Angaben:
    
    
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
    <td><p><strong>Erstellen</strong></p></td>
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
    <td><p><strong>Wertdaten</strong></p></td>
    <td><p>00000000</p></td>
    </tr>
    </tbody>
    </table>


8.  Klicken Sie zum Speichern der Änderungen auf **OK** und schließen Sie dann das Gruppenrichtlinienobjekt.

Anschließend müssen Sie das erstellte Gruppenrichtlinienobjekt mit der Gruppe der Benutzer (beispielsweise einer Organisationseinheit) verbinden, denen Sie die Richtlinie zuweisen möchten.

**So verwenden Sie das Gruppenrichtlinienobjekt zum Zuweisen der Richtlinie**

1.  Klicken Sie in der Gruppenrichtlinien-Verwaltungskonsole mit der rechten Maustaste auf die Organisationseinheit, der Sie die Richtlinie zuweisen möchten, und wählen Sie dann **Verknüpfung mit einem vorhandenen Gruppenrichtlinienobjekt** aus.

2.  Wählen Sie im Dialogfeld **Gruppenrichtlinienobjekt auswählen** das von Ihnen erstellte Gruppenrichtlinienobjekt und anschließend **OK** aus.

3.  Öffnen Sie auf dem Computer des Zielbenutzers eine Eingabeaufforderung und geben Sie den folgenden Befehl ein:
    
    **gpupdate /target:user**
    
    Die Meldung „Richtlinie wird aktualisiert..." wird angezeigt, während das GPO angewendet wird. Wenn der Vorgang abgeschlossen ist, erscheint die Meldung „Die Aktualisierung der Benutzerrichtlinie wurde abgeschlossen".

4.  Geben Sie an der Eingabeaufforderung den folgenden Befehl ein:
    
    **gpresult /r**
    
    Ihnen sollte nun „Zugewiesene Gruppenrichtlinienobjekte" mit dem Namen des von Ihnen erstellten Gruppenrichtlinienobjekts darunter angezeigt werden.

Um festzustellen, ob das GPO die Registrierung auf dem Computer des Benutzers erfolgreich aktualisiert hat, überprüfen Sie die Registrierung entsprechend. Öffnen Sie den ** \[\_Registrierungs-Editor, und navigieren\_Sie\\zum\\HKEY\\-\\aktuellen\] Benutzer Software-Microsoft Office lync** -Schlüssel. Wenn das GPO die Registrierung erfolgreich aktualisiert hat, erscheint unter „EnableSkypeUI" der Wert „0".

</div>

</div>

<span> </span>

</div>

</div>

</div>

