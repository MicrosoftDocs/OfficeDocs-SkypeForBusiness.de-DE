---
title: Erstellen oder Ändern einer neuen Clientversionsrichtlinie
TOCTitle: Erstellen oder Ändern einer neuen Clientversionsrichtlinie
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ898476(v=OCS.15)
ms:contentKeyID: 52056331
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Ändern einer neuen Clientversionsrichtlinie

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Clientversionsrichtlinien dienen zum Festlegen der in Ihrer Umgebung unterstützten Clientversionen. Das Verwenden der Clientversionsverwaltung kann zum Reduzieren der Kosten für die Unterstützung mehrerer Clientversionen beitragen. Außerdem lässt sich damit die allgemeine Benutzerfreundlichkeit verbessern, da bei der Interaktion zweier Clients unterschiedlicher Versionen die für einen der Clients verfügbaren Funktionen durch die Funktionen des anderen Clients eingeschränkt werden können. Clientversionsrichtlinien können Sie in der Systemsteuerung für Lync Server 2013 oder in der Verwaltungsshell für Lync Server 2013 erstellen oder ändern.

## So erstellen oder ändern Sie Clientversionsrichtlinien mithilfe der Lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**.
    

    > [!NOTE]
    > Die Registerkarte <STRONG>Clientversionsrichtlinie</STRONG> ist standardmäßig ausgewählt.



4.  Führen Sie auf der Seite **Clientversionsrichtlinie** eine der folgenden Aktionen aus:
    
      - Klicken Sie zum Erstellen einer Clientversionsrichtlinie auf **Neu**, wählen Sie die Option **Standortrichtlinie**, **Poolrichtlinie** oder **Benutzerrichtlinie** aus, und klicken Sie dann auf **OK**.
    
      - Zum Ändern der globalen Richtlinie oder einer anderen vorhandenen Clientversionsrichtlinie wählen Sie die entsprechende Richtlinie aus, klicken auf **Bearbeiten** und dann auf **Details anzeigen**.

5.  Erstellen oder ändern Sie Regeln auf der Seite **Clientversionsrichtlinie bearbeiten** gemäß der Beschreibung in [Erstellen oder Ändern einer neuen Regel für Clientversionsrichtlinien](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).

## Erstellen oder Ändern von Clientversionsrichtlinien mithilfe von Windows PowerShell-Cmdlets

Sie können Clientversionsrichtlinien mit dem Cmdlet **New-CsClientVersionPolicy** erstellen und sie dann mit dem Cmdlet **Set-CsClientVersionPolicy** ändern. Diese Cmdlets können Sie entweder in der Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So erstellen Sie eine neue Clientversionsrichtlinie mit Standortbereichszuweisung

  - Mit dem folgenden Befehl wird eine neue Clientversionsrichtlinie auf den Standort Redmond angewendet. Da keine zusätzlichen Parameter angegeben sind, werden die Standardeinstellungen der Clientversion für die neue Richtlinie verwendet.
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

## So erstellen Sie eine neue benutzerbasierte Clientversionsrichtlinie

  - Zum Erstellen einer benutzerbasierten Clientversionsrichtlinie verwenden Sie einen Befehl wie den folgenden:
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

Einzelheiten dazu finden Sie in den Hilfethemen zu den Cmdlets [New-CsClientVersionPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientVersionPolicy) und [Set-CsClientVersionPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientVersionPolicy).

