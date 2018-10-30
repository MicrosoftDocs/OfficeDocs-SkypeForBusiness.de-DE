---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren des Zugriffs durch anonyme Benutzer'
TOCTitle: Aktivieren oder Deaktivieren des Zugriffs durch anonyme Benutzer
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49295856
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren oder Deaktivieren des Zugriffs durch anonyme Benutzer in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Anonyme Benutzer sind Benutzer, die nicht über ein Benutzerkonto in Active Directory-Domänendienste Ihrer Organisation oder in einer unterstützten Partnerdomäne verfügen, aber zur Remoteteilnahme an einer lokalen Konferenz eingeladen werden können. Wenn Sie die anonyme Teilnahme an Besprechungen zulassen, können anonyme Benutzer (also Benutzer, deren Identität nur durch den Besprechungs- oder Konferenzschlüssel bestätigt wird) an Besprechungen teilnehmen. Um die anonyme Teilnahme zuzulassen, müssen Sie diese Option für Ihre Organisation aktivieren.

Wenn Sie den Zugriff durch anonyme Benutzer zu einem späteren Zeitpunkt temporär oder dauerhaft unterbinden möchten, können Sie die Option für Ihre Organisation deaktivieren. Verwenden Sie das Verfahren in diesem Abschnitt, um den Zugriff durch anonyme Benutzer für Ihre Organisation zu aktivieren oder zu deaktivieren.


> [!NOTE]
> Durch Aktivieren des Zugriffs durch anonyme Benutzer für Ihre Organisation geben Sie lediglich an, dass Ihre Server, auf denen der Zugriffs-Edgedienst ausgeführt wird, den Zugriff durch anonyme Benutzer unterstützen. Anonyme Benutzer können erst an Besprechungen in Ihrer Organisation teilnehmen, wenn Sie zusätzlich mindestens eine Konferenzrichtlinie konfigurieren und auf einen oder mehrere Benutzer oder Benutzergruppen anwenden. Nur Benutzer, denen eine Konferenzrichtlinie zur Unterstützung anonymer Benutzer zugeordnet ist, können anonyme Benutzer zu Besprechungen einladen. Ausführliche Informationen zum Konfigurieren von Konferenzrichtlinien zur Unterstützung des Einladens von anonymen Benutzern finden Sie unter <A href="lync-server-2013-conferencing-policies.md">Konferenzrichtlinien in Lync Server 2013</A>.



## So aktivieren oder deaktivieren Sie den Zugriff durch anonyme Benutzer für Ihre Organisation

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Konfiguration für Zugriffsedge** .

4.  Klicken Sie auf der Seite **Konfiguration für Zugriffsedge** auf **Global** , klicken Sie auf **Bearbeiten** , und klicken Sie dann auf **Details anzeigen** .

5.  Führen Sie im Abschnitt **Konfiguration für Zugriffsedge bearbeiten** eine der folgenden Aktionen aus:
    
      - Aktivieren Sie das Kontrollkästchen **Kommunikation mit anonymen Benutzern aktivieren** , um den Zugriff durch anonyme Benutzer für Ihre Organisation zu aktivieren.
    
      - Deaktivieren Sie das Kontrollkästchen **Kommunikation mit anonymen Benutzern aktivieren** , um den Zugriff durch anonyme Benutzer für Ihre Organisation zu deaktivieren.

6.  Klicken Sie auf **Commit** .

## Aktivieren oder Deaktivieren des Zugriffs durch anonyme Benutzer mithilfe der Windows PowerShell-Cmdlets

Sie können den Zugriff durch anonyme Benutzer mithilfe von Windows PowerShell und des **Set-CsAccessEdgeConfiguration**-Cmdlets verwalten. Dieses Cmdlet können Sie entweder in der Verwaltungsshell für Lync Server 2013 ausführen oder in einer Remotesitzung von Windows PowerShell. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So aktivieren Sie den Zugriff durch anonyme Benutzer

  - Zum Aktivieren des Zugriffs durch anonyme Benutzer legen Sie den Wert der **AllowAnonymousUsers**-Eigenschaft auf **True** **($True)** fest:
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## So deaktivieren Sie den Zugriff durch anonyme Benutzer

  - Zum Deaktivieren des Zugriffs durch anonyme Benutzer legen Sie den Wert der **AllowAnonymousUsers**-Eigenschaft auf **False** **($False)** fest:
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

## Siehe auch

#### Konzepte

[Referenz zu den Konferenzrichtlinieneinstellungen](lync-server-2013-conferencing-policy-settings-reference.md)

