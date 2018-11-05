---
title: 'Lync Server 2013: Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer zu einem für Lync aktivierten Benutzer'
TOCTitle: Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer zu einem für Lync aktivierten Benutzer
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398551(v=OCS.15)
ms:contentKeyID: 49294415
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer zu einem für Lync aktivierten Benutzer in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

Wurde ein Benutzer für Lync Server aktiviert, können Sie den SIP-Partnerverbund, den XMPP-Partnerverbund, den Zugriff durch Remotebenutzer und Verbindungen mit öffentlichen Instant Messaging-Diensten in Lync Server-Systemsteuerung konfigurieren, indem Sie bestimmten Benutzern die entsprechenden Richtlinien zuweisen. Wenn Sie beispielsweise eine Richtlinie für die Unterstützung des Remotebenutzerzugriffs erstellt haben, müssen Sie diese auf den Benutzer anwenden, damit der Benutzer von einem Remotestandort aus eine Verbindung mit Lync Server herstellen und mit internen Benutzern zusammenarbeiten kann.


> [!NOTE]
> Um den Zugriff durch externe Benutzer zu unterstützen, müssen Sie die Unterstützung für jeden Typ des externen Benutzerzugriffs aktivieren, der unterstützt werden soll, sowie die entsprechenden Richtlinien und andere Optionen zur Verwendungssteuerung konfigurieren. Ausführliche Informationen hierzu finden Sie unter <A href="lync-server-2013-configuring-support-for-external-user-access.md">Konfigurieren der Unterstützung für den externen Benutzerzugriff in Lync Server 2013</A> in der Bereitstellungsdokumentation oder unter <A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">Verwalten von Partnerverbünden und externem Zugriff auf Lync Server 2013</A> in der Betriebsdokumentation.



Verwenden Sie das Verfahren in diesem Thema, um eine zuvor erstellte Richtlinie für den externen Benutzerzugriff auf ein oder mehrere Benutzerkonten anzuwenden.

## So wenden Sie eine Richtlinie für den externen Benutzerzugriff auf ein Benutzerkonto an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer** , und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.

4.  Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen** .

5.  Wählen Sie in **Lync Server-Benutzer bearbeiten** unter **Richtlinie für den externen Zugriff** die Benutzerrichtlinie aus, die Sie anwenden möchten.
    

    > [!NOTE]
    > Mit den Einstellungen <STRONG>&lt;Automatisch&gt;</STRONG> werden die Standardeinstellungen des Servers oder die globalen Richtlinieneinstellungen angewendet.



## Zuweisen von Richtlinien für den externen Zugriff auf Benutzerbasis mithilfe von Windows PowerShell-Cmdlets

Richtlinien für den externen Zugriff auf Benutzerebene können über die Windows PowerShell und das CsExternalAccessPolicy-Cmdlet zugewiesen werden. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So weisen Sie einem einzelnen Benutzer eine Richtlinie für den externen Zugriff auf Benutzerebene zu

  - Mit diesem Befehl wird dem Benutzer "Ken Myer" die Richtlinie „RedmondExternalAccessPolicy“ für den externen Zugriff auf Benutzerebene zugewiesen.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

## So weisen Sie mehreren Benutzern eine Richtlinie für den externen Zugriff auf Benutzerebene zu

  - Mit diesem Befehl wird die Richtlinie "USAExternalAccessPolicy" für den externen Zugriff auf Benutzerebene allen Benutzern zugewiesen, die Active Directory ein Konto in der Organisationseinheit "UnitedStates" besitzen. Weitere Informationen zu dem in diesem Befehl verwendeten OU-Parameter finden Sie in der Dokumentation zum [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser)-Cmdlet.
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

## So heben Sie die Zuweisung einer Richtlinie für den externen Zugriff auf Benutzerbasis auf

  - Mit diesem Befehl wird die Zuweisung sämtlicher Richtlinien für den externen Zugriff auf Benutzerebene, die dem Benutzer Ken Myer zuvor zugeordnet wurden, aufgehoben. Nach der Aufhebung der Richtlinie auf Benutzerebene wird Ken Myer automatisch unter Verwendung der globalen Richtlinie bzw. (sofern vorhanden) von der Richtlinie seines lokalen Standorts verwaltet. Die Standortrichtlinie hat Vorrang vor der globalen Richtlinie.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

Weitere Informationen finden Sie in dem Hilfethema zum [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)-Cmdlet.

