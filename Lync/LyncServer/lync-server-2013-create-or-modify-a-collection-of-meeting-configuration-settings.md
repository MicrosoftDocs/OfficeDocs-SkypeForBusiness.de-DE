---
title: Erstellen oder Ändern einer Sammlung von Konfigurationseinstellungen für Besprechungen
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
ms.openlocfilehash: 0a5f80066a68b45e062a351478bea93a5c2e8fd0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763337"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-meeting-configuration-settings-in-lync-server-2013"></a>Erstellen oder Ändern einer Sammlung von Einstellungen für die besprechungskonfiguration in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Sie können die Einstellungen auf der Seite "besprechungskonfiguration" verwenden, um verschiedene Merkmale der Besprechungsteilnahme zu definieren. Standardmäßig definieren die globalen Einstellungen die Verknüpfungs Umgebung. Sie können auch Einstellungen auf Websiteebene und auf Poolebene für Besprechungen erstellen. Wenn Sie Einstellungen auf der Poolebene erstellen, gelten diese für alle Besprechungen, die von dem jeweiligen Pool gehostet werden. Wenn Sie keine Einstellungen auf der Poolebene erstellen, gelten die auf der Standortebene definierten Einstellungen (sofern vorhanden). Sind keine Einstellungen auf der Standortebene definiert, werden die globalen Einstellungen auf sämtliche Besprechungen angewendet.

<div>

## <a name="to-create-new-meeting-join-settings"></a>So erstellen Sie neue Besprechungs Verknüpfungseinstellungen

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenzen** , und klicken Sie dann auf **besprechungskonfiguration**.

4.  Klicken Sie auf der Seite **Besprechungskonfiguration** auf **Neu** und führen Sie eine der folgenden Aktionen aus:
    
      - Klicken Sie auf **Standortkonfiguration**, um eine Richtlinie auf Standortebene zu erstellen. Geben Sie im Suchfeld **Standort auswählen** einen Teil oder den gesamten Namen des Standorts ein, für den Sie Einstellungen für den Besprechungsbeitritt definieren möchten. Klicken Sie in der resultierenden Liste der Standorte auf den gewünschten Standort und klicken Sie auf **OK**.
    
      - Klicken Sie auf **Poolkonfiguration**, um eine Richtlinie auf Poolebene zu erstellen. Geben Sie im Suchfeld **Dienst auswählen** einen Teil oder den gesamten Namen des Pooldienstes ein, für den Sie Einstellungen für den Besprechungsbeitritt definieren möchten. Klicken Sie in der resultierenden Liste der Dienste auf den gewünschten Pool und klicken Sie auf **OK**.

5.  Deaktivieren Sie das Kontrollkästchen **PSTN-Anrufer umgehen Wartebereich**, um Teilnehmer, die sich über das Festnetz einwählen, zunächst an den Wartebereich weiterzuleiten. In der Standardeinstellung gelangen Anrufer, die sich über das Festnetz einwählen, direkt zur Besprechung.

6.  Legen Sie im Abschnitt **Als Referenten festlegen** fest, wer in der Besprechung als Referent agieren kann:
    
      - Klicken Sie auf **Keiner**, um nur dem Organisator die Rolle des Referenten zuzuweisen.
    
      - Klicken Sie auf **Unternehmen**, um nur denjenigen Teilnehmern die Funktion des Referenten zu ermöglichen, die Mitglieder Ihrer Organisation sind. Dies ist die Standardeinstellung.
    
      - Klicken Sie auf **Jeder**, um allen Teilnehmern das Agieren als Referent zu ermöglichen.

7.  Wenn der Organisator bei der Planung einer Besprechung einen Konferenztyp auswählen soll, deaktivieren Sie das Kontrollkästchen **Konferenztyp standardmäßig zugewiesen**. In der Standardeinstellung wird der Konferenztyp automatisch zugewiesen.

8.  Wenn Sie verhindern möchten, dass anonyme (nicht authentifizierte) Benutzer automatisch zugelassen werden, deaktivieren Sie das Kontrollkästchen **Anonyme Benutzer standardmäßig zulassen**. In der Standardeinstellung werden anonyme Benutzer automatisch für Besprechungen zugelassen.

9.  Führen Sie die folgenden Schritte aus, um die Besprechungseinladung anzupassen, die an die Teilnehmer gesendet wird. Beachten Sie, dass für URLs und den benutzerdefinierten Fußzeilentext eine maximale Größe von 1 KB gilt. Wenn Sie, mit Ausnahme von **Hilfe-URL**, keinen Wert für die Anpassungen angeben, werden sie nicht in die Besprechung aufgenommen. Wenn Sie keine benutzerdefinierte Hilfe-URL angeben, wird die standardmäßige Hilfe-URL für lync in der Einladung angezeigt.
    
      - Zum Anpassen des Logos, das in der Besprechungseinladung angezeigt wird, geben Sie in **Logo-URL** den Speicherort des Logos ein.
        
        <div>
        

        > [!NOTE]
        > Das Logo muss ein GIF- oder JPG-Bild mit einer Größe von 188 x 30 Pixel sein.

        
        </div>
    
      - Zum Anpassen des Hilfetexts, der in der Besprechungseinladung angezeigt wird, geben Sie in **Hilfe-URL** den Speicherort des Hilfetexts ein.
    
      - Zum Anpassen der rechtlichen Hinweise, die in der Besprechungseinladung angezeigt werden, geben Sie in **URL zu rechtlichen Hinweisen** den Speicherort der rechtlichen Hinweise ein.
    
      - Zum Anpassen des Fußzeilentexts, der in der Besprechungseinladung angezeigt wird, geben Sie in **Benutzerdefinierter Fußzeilentext** Text ein.

10. Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="to-modify-an-existing-collection-of-meeting-configurations"></a>So ändern Sie eine vorhandene Sammlung von Besprechungs Konfigurationen

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenzen** , und klicken Sie dann auf **besprechungskonfiguration**.

4.  Klicken Sie in der Liste mit den Besprechungskonfigurationen auf die Konfiguration, die Sie ändern möchten, klicken Sie auf **Bearbeiten** und dann auf **Details einblenden**.

5.  Ändern Sie in **Besprechungskonfiguration bearbeiten** beliebige Konfigurationseinstellungen. Hiervon ausgenommen ist der Konfigurationsname, dieser kann nicht geändert werden.

6.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="creating-new-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a>Erstellen von neuen Besprechungs Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets

Die Einstellungen für die besprechungskonfiguration können mit Windows PowerShell und dem Cmdlet New-CsMeetingConfiguration (nur im Website Bereich) erstellt werden. Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-create-meeting-configuration-settings-that-use-the-default-values"></a>So erstellen Sie Besprechungs Konfigurationseinstellungen, die die Standardwerte verwenden

  - Dieser Befehl erstellt einen neuen Satz von Besprechungs Konfigurationseinstellungen für die Website "Redmond":
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    Da im vorherigen Befehl keine weiteren Parameter (außer dem obligatorischen Identity-Parameter) angegeben wurden, werden in den neuen Besprechungskonfigurationseinstellungen für alle Eigenschaften die Standardwerte verwendet.

</div>

<div>

## <a name="to-change-a-property-value-when-creating-meeting-configuration-settings"></a>So ändern Sie einen Eigenschaftswert beim Erstellen von Besprechungs Konfigurationseinstellungen

  - Um Einstellungen zu erstellen, die andere Eigenschaftswerte verwenden, geben Sie einfach den entsprechenden Parameter und Parameterwert ein. Wenn Sie beispielsweise eine Auflistung von Besprechungskonfigurationseinstellungen erstellen möchten, die standardmäßig jeden als Referent zu einer Besprechung zulassen, verwenden Sie den folgenden Befehl:
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-meeting-configuration-settings"></a>So ändern Sie beim Erstellen von Besprechungs Konfigurationseinstellungen mehrere Eigenschaftswerte

  - Mehrere Eigenschaftswerte können geändert werden, indem Sie mehrere Parameter angeben. Dieser Befehl gibt beispielsweise jeder zu einer Besprechung als Referent an und erzwingt auch, dass PSTN-Benutzer in der Lobby warten, bis Sie formell zur Besprechung zugelassen sind:
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

</div>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [New-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

