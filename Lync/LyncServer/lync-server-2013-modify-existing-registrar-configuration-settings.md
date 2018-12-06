---
title: Ändern von vorhandenen Registrierungskonfigurationseinstellungen
TOCTitle: Ändern von vorhandenen Registrierungskonfigurationseinstellungen
ms:assetid: a8931511-3e66-49ed-a3ec-03bcd61ce1f0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182566(v=OCS.15)
ms:contentKeyID: 49295022
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ändern von vorhandenen Registrierungskonfigurationseinstellungen

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Mithilfe der Registrierung können Sie Proxyserver-Authentifizierungsprotokolle konfigurieren. Informationen zu den verfügbaren Protokollen finden Sie unter [Erstellen von Registrierungskonfigurationseinstellungen](lync-server-2013-create-registrar-configuration-settings.md).


> [!NOTE]
> Es wird empfohlen, sowohl Kerberos als auch NTLM zu aktivieren, wenn ein Server die Authentifizierung von Remote- und Unternehmensclients unterstützt. Durch eine Kommunikation des Edgeservers mit den internen Servern wird gewährleistet, dass Remoteclients nur die NTLM-Authentifizierung verwenden können. Wenn auf diesen Servern nur Kerberos verwendet wird, ist eine Authentifizierung von Remotebenutzern nicht möglich. Wenn Unternehmensbenutzer sich ebenfalls über den Server authentifizieren, wird Kerberos verwendet.



Führen Sie die folgenden Schritte aus, um eine vorhandene Registrierung zu ändern.

## So ändern Sie eine vorhandene Registrierung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer des Netzwerks an, in dem Sie Lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Registrierung**.

4.  Klicken Sie auf der Seite **Registrierung** auf einen Dienst, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  Wählen Sie im Abschnitt **Registrierungseinstellung bearbeiten**, je nach Funktionen der Clients und der Unterstützung in Ihrer Umgebung, eine oder mehrere der folgenden Optionen:
    
      - **Kerberos-Authentifizierung aktivieren** – Die Server im Pool verwenden für Authentifizierungsanforderungen das Kerberos-Protokoll.
    
      - **NTLM-Authentifizierung aktivieren** – Die Server im Pool verwenden für Authentifizierungsanforderungen das NTLM-Protokoll.
    
      - **Zertifikatauthentifizierung aktivieren** – Die Server im Pool geben Zertifikate an die Clients aus.

6.  Klicken Sie auf **Commit**.

