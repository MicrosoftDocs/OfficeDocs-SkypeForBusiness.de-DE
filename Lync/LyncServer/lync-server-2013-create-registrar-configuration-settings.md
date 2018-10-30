---
title: Erstellen von Registrierungskonfigurationseinstellungen
TOCTitle: Erstellen von Registrierungskonfigurationseinstellungen
ms:assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182601(v=OCS.15)
ms:contentKeyID: 49295817
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen von Registrierungskonfigurationseinstellungen

 

_**Letztes Änderungsdatum des Themas:** 2013-03-17_

Mithilfe der Registrierung können Sie Proxyserver-Authentifizierungsmethoden konfigurieren. Das angegebene Authentifizierungsprotokoll legt fest, welche Art von Authentifizierungsanforderungen die Server im Pool an die Clients senden. Die folgenden Protokolle sind verfügbar:

  - **Kerberos**   Das stärkste Authentifizierungsschema auf Grundlage von Kennwörtern, das für Clients verwendet werden kann. Es ist normalerweise jedoch nur für interne Clients verfügbar, da eine Clientverbindung mit einem Schlüsselverteilungscenter (Kerberos-Domänencontroller) erforderlich ist. Diese Einstellung ist dann geeignet, wenn der Server nur Unternehmensclients authentifiziert.

  - **NTLM**   Bietet eine kennwortbasierte Authentifizierung für Clients, die für das Kennwort ein Hashingschema mit Abfrage/Rückmeldung verwenden. Für Clients ohne Verbindung mit einem Schlüsselverteilungscenter (Kerberos-Domänencontroller), beispielsweise für Remotebenutzer, steht nur diese Form der Authentifizierung zur Verfügung. Wenn ein Server ausschließlich Remotebenutzer authentifiziert, sollten Sie NTLM auswählen.

  - **Zertifikatauthentifizierung**   Dies ist die neue Authentifizierungsmethode, wenn der Server Zertifikate von Lync Phone Edition-Clients, Telefonen in öffentlichen Bereichen und Lync 2013 abrufen muss. Auf Lync Phone Edition-Clients stellt Lync Server 2013 nach der Anmeldung des Benutzers und einer erfolgreichen PIN-Authentifizierung den SIP-URI für das Telefon bereit und gibt ein signiertes Lync Server-Zertifikat oder ein Benutzerzertifikat aus, das Joe (z. B. SN=joe@contoso.com) gegenüber dem Telefon identifiziert. Dieses Zertifikat wird für die Authentifizierung beim Registrierungsdienst und den Webdiensten verwendet.


> [!NOTE]
> Es wird empfohlen, sowohl Kerberos als auch NTLM zu aktivieren, wenn ein Server die Authentifizierung von Remote- und Unternehmensclients unterstützt. Durch eine Kommunikation des Edgeservers mit den internen Servern wird gewährleistet, dass Remoteclients nur die NTLM-Authentifizierung verwenden können. Wenn auf diesen Servern nur Kerberos verwendet wird, ist eine Authentifizierung von Remotebenutzern nicht möglich. Wenn Unternehmensbenutzer sich ebenfalls über den Server authentifizieren, wird Kerberos verwendet.



Führen Sie die folgenden Schritte aus, um eine neue Registrierung zu erstellen.

## So erstellen Sie eine Registrierung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer des Netzwerks an, in dem Sie Lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Registrierung**.

4.  Klicken Sie auf der Seite **Registrierung** auf **Neu**.

5.  Klicken Sie in **Dienst auswählen** auf den Dienst, auf den die Registrierung angewendet werden soll, und anschließend auf **OK**.

6.  Wählen Sie im Abschnitt **Neue Registrierungseinstellung**, je nach Funktionen der Clients und der Unterstützung in Ihrer Umgebung, eine oder mehrere der folgenden Optionen:
    
      - **Kerberos-Authentifizierung aktivieren** – Die Server im Pool verwenden für Authentifizierungsanforderungen das Kerberos-Protokoll.
    
      - **NTLM-Authentifizierung aktivieren** – Die Server im Pool verwenden für Authentifizierungsanforderungen das NTLM-Protokoll.
    
      - **Zertifikatauthentifizierung aktivieren** – Die Server im Pool geben Zertifikate an die Clients aus.

7.  Klicken Sie auf **Commit**.

