---
title: Erstellen von neuen Webdienst-Konfigurationseinstellungen
TOCTitle: Erstellen von neuen Webdienst-Konfigurationseinstellungen
ms:assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182605(v=OCS.15)
ms:contentKeyID: 49295893
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen von neuen Webdienst-Konfigurationseinstellungen

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Sie können auf der Seite **Webdienst** die Authentifizierungsmethoden für den Zugriff auf Lync Server 2013-bezogene Webserver und Webdienste konfigurieren.

Führen Sie die folgenden Schritte aus, um eine neue Webdienstrichtlinie zu erstellen.

## So erstellen Sie eine Webdienstrichtlinie

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer des Netzwerks an, in dem Sie Lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Webdienst**.

4.  Klicken Sie auf der Seite **Webdienst** auf **Neu**, und führen Sie eine der folgenden Aktionen aus:
    
      - Zum Konfigurieren des Webdiensts für einen Standort klicken Sie auf **Standortkonfiguration**. Klicken Sie in **Standort auswählen** auf den Standort, auf den die Webdienstrichtlinie angewendet werden soll, und anschließend auf **OK**.
    
      - Zum Konfigurieren des Webdiensts für einen Pool klicken Sie auf **Poolkonfiguration**. Klicken Sie in **Dienst auswählen** auf den Dienst, auf den die Webdienstrichtlinie angewendet werden soll, und anschließend auf **OK**.

5.  Wählen Sie im Abschnitt **Neue Webdiensteinstellung** unter **Integrierte Windows-Authentifizierung** die Option **Aushandeln**, **Integrierte Windows-Authentifizierung** oder **Keine** aus.

6.  Wählen Sie je nach Funktionen der Clients und der Unterstützung in Ihrer Umgebung, eine oder mehrere der folgenden Optionen:
    
      - **PIN-Authentifizierung aktivieren** – Clients werden über eine PIN authentifiziert.
    
      - **Zertifikatauthentifizierung aktivieren** – Die Server im Pool geben Zertifikate an die Clients aus.
    
      - **Download einer Zertifikatkette aktivieren** – Server können die Zertifikatkette für das jeweilige Zertifikat herunterladen.

7.  Klicken Sie auf **Commit**.

