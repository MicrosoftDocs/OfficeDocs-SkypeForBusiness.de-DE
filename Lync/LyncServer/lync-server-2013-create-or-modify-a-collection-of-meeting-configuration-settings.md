---
title: Erstellen oder Ändern einer Sammlung von Besprechungs Konfigurationseinstellungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of meeting configuration settings
ms:assetid: ce6773c1-a0d5-4405-8e32-33a6f3a46a1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721889(v=OCS.15)
ms:contentKeyID: 49733822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82520ea030dcfacdea1a5eb13608df8b827fe27a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-meeting-configuration-settings-in-lync-server-2013"></a>Erstellen oder Ändern einer Sammlung von Besprechungs Konfigurationseinstellungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Sie können die Einstellungen auf der Seite besprechungskonfiguration verwenden, um verschiedene Merkmale der Besprechungsteilnahme zu definieren. Standardmäßig definieren die globalen Einstellungen die Verknüpfungs Umgebung. Sie können auch Besprechungs Verknüpfungseinstellungen auf Websiteebene und Poolebene erstellen. Wenn Sie Einstellungen auf Poolebene erstellen, gelten diese Einstellungen für alle Besprechungen, die von diesem Pool gehostet werden. Wenn Sie keine Einstellungen auf Poolebene erstellen, gelten die Einstellungen auf Websiteebene, sofern vorhanden. Wenn Sie keine Einstellungen auf Websiteebene definieren, gelten die globalen Einstellungen für alle Besprechungen.

<div>

## <a name="to-create-new-meeting-join-settings"></a>So erstellen Sie neue Einstellungen für den besprechungsbeitritt

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **Besprechungskonfiguration**.

4.  Klicken Sie auf der Seite **besprechungskonfiguration** auf **neu**, und führen Sie eine der folgenden Aktionen aus:
    
      - Klicken Sie auf **Websitekonfiguration**, um eine Richtlinie auf Standortebene zu erstellen. Geben Sie im Feld **Website Suche auswählen** den vollständigen oder Teil des Namens der Website ein, für die Sie die Einstellungen für den besprechungsbeitritt definieren möchten. Klicken Sie in der resultierenden Liste der Standorte auf den gewünschten Standort, und klicken Sie auf **OK**.
    
      - Klicken Sie zum Erstellen einer Richtlinie auf Poolebene auf **Poolkonfiguration**. Geben Sie im Suchfeld **Dienst auswählen einen** Teil oder den vollständigen Namen des Pool Diensts ein, für den Sie die Einstellungen für den besprechungsbeitritt definieren möchten. Klicken Sie in der daraufhin angezeigten Liste mit den Diensten auf den gewünschten Pool, und klicken Sie dann auf **OK**.

5.  Deaktivieren Sie das Kontrollkästchen **PSTN-Anrufer umgehen Lobby**, um Teilnehmer, die sich über das Festnetz einwählen, zunächst an die Lobby weiterzuleiten. In der Standardeinstellung gelangen Anrufer, die sich über das Festnetz einwählen, direkt zur Besprechung.

6.  Legen Sie im Abschnitt **Als Referent benennen** fest, wer in der Besprechung als Referent agieren kann:
    
      - Klicken Sie auf **Keiner**, um nur dem Organisator die Rolle des Referenten zuzuweisen.
    
      - Klicken Sie auf **Unternehmen**, um nur denjenigen Teilnehmern die Funktion des Referenten zu ermöglichen, die Mitglieder Ihrer Organisation sind. Dies ist die Standardeinstellung.
    
      - Klicken Sie auf **Jeder**, um allen Teilnehmern das Agieren als Referent zu ermöglichen.

7.  Wenn der Organisator bei der Planung einer Besprechung einen Konferenztyp auswählen soll, deaktivieren Sie das Kontrollkästchen **Konferenztyp standardmäßig zuweisen**. In der Standardeinstellung wird der Konferenztyp automatisch zugewiesen.

8.  Wenn Sie verhindern möchten, dass anonyme (nicht authentifizierte) Benutzer automatisch zugelassen werden, deaktivieren Sie das Kontrollkästchen **Anonyme Benutzer standardmäßig zulassen**. In der Standardeinstellung werden anonyme Benutzer automatisch für Besprechungen zugelassen.

9.  Gehen Sie folgendermaßen vor, um die Besprechungseinladung anzupassen, die an die Teilnehmer gesendet wird. Beachten Sie, dass die maximale Länge für URLs und benutzerdefinierter Fußzeilentext 1KB ist. Wenn Sie für die Anpassungen keinen Wert angeben, werden diese nicht in die Besprechung aufgenommen, außer bei der **Hilfe-URL**. Wenn Sie keine benutzerdefinierte Hilfe-URL einschließen, wird die standardmäßige Hilfe-URL für lync in der Einladung angezeigt.
    
      - Um das Logo anzupassen, das in der Besprechungseinladung angezeigt wird, geben Sie in **Logo-URL**den Speicherort des Logos ein.
        
        <div>
        

        > [!NOTE]
        > Das Logo muss ein GIF-oder JPG-Bild mit einer Größe von 188 x 30 Pixel sein.

        
        </div>
    
      - Um den Hilfetext anzupassen, der in der Besprechungseinladung angezeigt wird, geben Sie in der **Hilfe-URL**den Speicherort des Hilfetexts ein.
    
      - Um den rechtlichen Text anzupassen, der in der Besprechungseinladung angezeigt wird, geben Sie unter **rechtlicher Text**die Adresse des rechtlichen Texts ein.
    
      - Zum Anpassen des Fußzeilentexts, der in der Besprechungseinladung angezeigt wird, geben Sie in **benutzerdefinierter Fußzeilen**Text Text ein.

10. Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="to-modify-an-existing-collection-of-meeting-configurations"></a>So ändern Sie eine vorhandene Sammlung von Besprechungs Konfigurationen

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **Besprechungskonfiguration**.

4.  Klicken Sie in der Liste der Besprechungs Konfigurationen auf die Konfiguration, die Sie ändern möchten, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  Ändern Sie in **besprechungskonfiguration bearbeiten**alle Konfigurationseinstellungen außer dem Konfigurationsnamen, der nicht geändert werden kann.

6.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="creating-new-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a>Erstellen neuer Besprechungs Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets

Besprechungs Konfigurationseinstellungen können (nur auf Standortebene) mithilfe Windows PowerShell und des Cmdlets New-CsMeetingConfiguration erstellt werden. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

<div>

## <a name="to-create-meeting-configuration-settings-that-use-the-default-values"></a>So erstellen Sie Besprechungs Konfigurationseinstellungen, die die Standardwerte verwenden

  - Mit diesem Befehl wird eine neue Gruppe von Besprechungs Konfigurationseinstellungen für den Standort "Redmond" erstellt:
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    Da im vorherigen Befehl keine Parameter (außer dem obligatorischen Identity-Parameter) angegeben wurden, werden in den neuen Besprechungs Konfigurationseinstellungen die Standardwerte für alle Eigenschaften verwendet.

</div>

<div>

## <a name="to-change-a-property-value-when-creating-meeting-configuration-settings"></a>So ändern Sie einen Eigenschaftswert beim Erstellen von Besprechungs Konfigurationseinstellungen

  - Zum Erstellen von Einstellungen, die verschiedene Eigenschaftswerte verwenden, geben Sie einfach den entsprechenden Parameter und den Parameterwert an. Um beispielsweise eine Sammlung von Besprechungs Konfigurationseinstellungen zu erstellen, die standardmäßig jeder zu einer Besprechung als Referent zulässt, verwenden Sie einen Befehl wie den folgenden:
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-meeting-configuration-settings"></a>So ändern Sie beim Erstellen von Besprechungs Konfigurationseinstellungen mehrere Eigenschaftswerte

  - Mehrere Eigenschaftswerte können durch die Angabe mehrerer Parameter geändert werden. Dieser Befehl gibt beispielsweise alle Personen zu einer Besprechung als Referenten an und zwingt PSTN-Benutzer dazu, in der Lobby zu warten, bis Sie offiziell zur Besprechung zugelassen sind:
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

</div>

Weitere Informationen finden Sie im Hilfethema zum [New-CsMeetingConfiguration-](https://technet.microsoft.com/library/Gg398065(v=OCS.15)) Cmdlet.

</div>

</div>

<span> </span>

</div>

</div>

</div>

