---
title: Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für Besprechungen
TOCTitle: Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für Besprechungen
ms:assetid: ce6773c1-a0d5-4405-8e32-33a6f3a46a1a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721889(v=OCS.15)
ms:contentKeyID: 49890946
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für Besprechungen

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Über die Einstellungen auf der Seite Besprechungskonfiguration werden verschiedene Merkmale für die Benutzerfreundlichkeit dieses Vorgangs definiert. Standardmäßig wird die Besprechungsteilnahme über die globalen Einstellungen definiert. Sie können jedoch auch Einstellungen für die Besprechungsteilnahme auf Standort- oder Poolebene festlegen. Wenn Sie Einstellungen auf Poolebene erstellen, gelten diese für alle Besprechungen, die von dem jeweiligen Pool gehostet werden. Wenn Sie keine Einstellungen auf Poolebene erstellen, gelten die auf Standortebene definierten Einstellungen (sofern vorhanden). Sind keine Einstellungen auf Standortebene definiert, werden die globalen Einstellungen auf sämtliche Besprechungen angewendet.

## So erstellen Sie neue Einstellungen für den Besprechungsbeitritt

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **Besprechungskonfiguration**.

4.  Klicken Sie auf der Seite **Besprechungskonfiguration** auf **Neu**, und führen Sie eine der folgenden Aktionen aus:
    
      - Klicken Sie auf **Standortkonfiguration**, um eine Richtlinie auf Standortebene zu erstellen. Geben Sie im Suchfeld **Standort auswählen** einen Teil oder den gesamten Namen des Standorts ein, für den Sie Einstellungen für den Besprechungsbeitritt definieren möchten. Klicken Sie in der resultierenden Liste der Standorte auf den gewünschten Standort, und klicken Sie auf **OK**.
    
      - Klicken Sie auf **Poolkonfiguration**, um eine Richtlinie auf Poolebene zu erstellen. Geben Sie im Suchfeld **Dienst auswählen** einen Teil oder den gesamten Namen des Pooldiensts ein, für den Sie Einstellungen für den Besprechungsbeitritt definieren möchten. Klicken Sie in der resultierenden Liste der Dienste auf den gewünschten Pool, und klicken Sie auf **OK**.

5.  Deaktivieren Sie das Kontrollkästchen **PSTN-Anrufer umgehen Wartebereich**, um Teilnehmer, die sich über das Festnetz einwählen, zunächst an den Wartebereich weiterzuleiten. In der Standardeinstellung gelangen Anrufer, die sich über das Festnetz einwählen, direkt zur Besprechung.

6.  Legen Sie im Abschnitt **Als Referenten festlegen** fest, wer in der Besprechung als Referent agieren kann:
    
      - Klicken Sie auf **Keiner**, um nur dem Organisator die Rolle des Referenten zuzuweisen.
    
      - Klicken Sie auf **Unternehmen**, um nur denjenigen Teilnehmern die Funktion des Referenten zu ermöglichen, die Mitglieder Ihrer Organisation sind. Dies ist die Standardeinstellung.
    
      - Klicken Sie auf **Jeder**, um allen Teilnehmern das Agieren als Referent zu ermöglichen.

7.  Wenn der Organisator bei der Planung einer Besprechung einen Konferenztyp auswählen soll, deaktivieren Sie das Kontrollkästchen **Konferenztyp standardmäßig zugewiesen**. In der Standardeinstellung wird der Konferenztyp automatisch zugewiesen.

8.  Wenn Sie verhindern möchten, dass anonyme (nicht authentifizierte) Benutzer automatisch zugelassen werden, deaktivieren Sie das Kontrollkästchen **Anonyme Benutzer standardmäßig zulassen**. In der Standardeinstellung werden anonyme Benutzer automatisch für Besprechungen zugelassen.

9.  Führen Sie die folgenden Schritte aus, um die Besprechungseinladung anzupassen, die an die Teilnehmer gesendet wird. Beachten Sie, dass für URLs und den benutzerdefinierten Fußzeilentext eine maximale Größe von 1 KB gilt. Wenn Sie, mit Ausnahme von **Hilfe-URL**, keinen Wert für die Anpassungen angeben, werden sie nicht in die Besprechung aufgenommen. Wenn Sie keine benutzerdefinierte Hilfe-URL angeben, wird die standardmäßige Hilfe-URL für Lync in der Besprechungseinladung angezeigt.
    
      - Zum Anpassen des Logos, das in der Besprechungseinladung angezeigt wird, geben Sie in **Logo-URL** den Speicherort des Logos ein.
        

        > [!NOTE]
        > Das Logo muss ein GIF- oder JPG-Bild mit einer Größe von 188&nbsp;x&nbsp;30&nbsp;Pixeln sein.

    
      - Zum Anpassen des Hilfetexts, der in der Besprechungseinladung angezeigt wird, geben Sie in **Hilfe-URL** den Speicherort des Hilfetexts ein.
    
      - Zum Anpassen der rechtlichen Hinweise, die in der Besprechungseinladung angezeigt werden, geben Sie in **URL zu rechtlichen Hinweisen** den Speicherort der rechtlichen Hinweise ein.
    
      - Zum Anpassen des Fußzeilentexts, der in der Besprechungseinladung angezeigt wird, geben Sie in **Benutzerdefinierter Fußzeilentext** Text ein.

10. Klicken Sie auf **Commit ausführen**.

## So ändern Sie eine vorhandene Auflistung von Besprechungskonfigurationen

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **Besprechungskonfiguration**.

4.  Klicken Sie in der Liste mit den Besprechungskonfigurationen auf die Konfiguration, die Sie ändern möchten, klicken Sie auf **Bearbeiten** und dann auf **Details einblenden**.

5.  Ändern Sie in **Besprechungskonfiguration bearbeiten** beliebige Konfigurationseinstellungen. Hiervon ausgenommen ist der Konfigurationsname, dieser kann nicht geändert werden.

6.  Klicken Sie auf **Commit ausführen**.

## Erstellen neuer Besprechungskonfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets

Besprechungskonfigurationseinstellungen können (nur auf Standortebene) mit der Windows PowerShell und dem New-CsMeetingConfiguration-Cmdlet erstellt werden. Dieses Cmdlet können Sie entweder über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So erstellen Sie Besprechungskonfigurationseinstellungen, die die Standardwerte verwenden

  - Mit diesem Befehl wird ein neuer Satz von Besprechungskonfigurationseinstellungen für den Standort "Redmond" erstellt:
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    Da im vorherigen Befehl keine weiteren Parameter (außer dem obligatorischen Identity-Parameter) angegeben wurden, werden in den neuen Besprechungskonfigurationseinstellungen für alle Eigenschaften die Standardwerte verwendet.

## So ändern Sie bei der Erstellung neuer Besprechungskonfigurationseinstellungen einen Eigenschaftswert

  - Um Einstellungen zu erstellen, die andere Eigenschaftswerte verwenden, geben Sie einfach den entsprechenden Parameter und Parameterwert ein. Wenn Sie beispielsweise eine Auflistung von Besprechungskonfigurationseinstellungen erstellen möchten, die standardmäßig jeden als Referent zu einer Besprechung zulassen, verwenden Sie den folgenden Befehl:
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

## So ändern Sie bei der Erstellung neuer Besprechungskonfigurationseinstellungen mehrere Eigenschaftswerte

  - Mehrere Eigenschaftswerte können geändert werden, indem Sie mehrere Parameter angeben. Beispielsweise wird mit dem folgenden Befehl jeder als Referent zu einer Besprechung zugelassen, und außerdem werden PSTN-Benutzer gezwungen, im Wartebereich zu warten, bis sie formell zur Besprechung zugelassen wurden:
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

Weitere Informationen finden Sie im Hilfethema für das [New-CsMeetingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMeetingConfiguration)-Cmdlet.

