---
title: 'Lync Server 2013: Übersicht über die Überwachung'
TOCTitle: Übersicht über die Überwachung
ms:assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204937(v=OCS.15)
ms:contentKeyID: 49890765
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Übersicht über die Überwachung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-05_

In Microsoft Lync Server 2013 werden mithilfe der Überwachung Nutzungsinformationen sowie QoE-Daten (Quality of Experience, Erlebnisqualität) für die Kommunikationssitzungen erfasst, die von den Benutzern unterhalten werden. Eine Sitzung ist ein allgemeiner Begriff, der sich auf die Verbindungen von Benutzern mit folgenden Elementen bezieht:

  - Konferenz

  - Konferenzmodalitäten (wie Audio/Video oder Anwendungsfreigabe)

  - Andere Benutzer über eine Peer-zu-Peer-Unterhaltung wie Sofortnachrichten oder Audioanruf


> [!NOTE]
> Lync Server 2013 protokolliert beispielsweise die folgenden Informationen über die jeweilige Sitzung: Wer hat wen angerufen? Welche Endpunkte waren an der Sitzung beteiligt? Wie lange hat die Sitzung gedauert? Wie wurde die Qualität der Sitzung empfunden? Der Anruf selbst wird von Lync Server jedoch nicht aufgezeichnet. Dies gilt auch für Sofortnachrichtensitzungen: Lync Server zeichnet zwar Informationen zu den Sofortnachrichtensitzungen auf, Datensätze für jede einzelne Sofortnachricht, die im Rahmen einer Sitzung gesendet wird, werden jedoch nicht verwaltet.



Die von Lync Server erfassten detaillierten Anrufinformationen können für verschiedene Zwecke wie die folgenden eingesetzt werden:

  - **Renditeanalyse (Return on Investment, ROI)** . Administratoren können die vom Monitoring Server erfassten Nutzungsdaten mit ähnlichen Daten aus früheren Telefoniesystemen vergleichen, um Kosteneinsparungen aufzuzeigen und Argumente für die Bereitstellung von Lync Server zu sammeln.

  - **Verwalten des Gerätebestands** . Informationen bezüglich der Inventarverwaltung unterstützen Administratoren bei der Identifizierung alter Geräte, die ersetzt werden müssen. Außerdem können auf diese Weise kostenintensive Geräte identifiziert werden, die anscheinend gar nicht genutzt werden.

  - Helpdesk. Informationen zur Problembehebung unterstützen Supporttechniker dabei, herauszufinden, warum beim Anruf eines Benutzers ein Fehler aufgetreten ist, ohne dass Protokolle vom Server oder Client angefordert werden müssen. Auf diese Informationen kann problemlos zugegriffen werden. Ferner sind die Angaben auch für Supportmitarbeiter ohne umfassende technische Kenntnisse von Microsoft Lync 2013 und Lync Server 2013 gut verständlich.

  - **Systemproblembehandlung** . Ermöglicht Administratoren das Erkennen grundlegender Probleme, die u. U. verhindern, dass Endbenutzer einfache Aufgaben wie das Beitreten zu einer Konferenz, das Tätigen eines Anrufs oder das Senden einer Sofortnachricht ausführen können.

Neben diesen Standardanrufinformationen stellt der Monitoring Server auch einen Mechanismus bereit, der SIP-Endpunkten (wie Lync 2013) das Bereitstellen von Informationen zur Problembehandlung erlaubt, auf die der Server anderweitig nicht zugreifen könnte:

  - **Medienmetriken mit Auswirkungen auf die Qualität** . Die Metriken beziehen sich auf die eigentliche Übertragung des Anrufs. Sie stellen eine Art "Reiseprotokoll" des Anrufs durch das Netzwerk dar und beinhalten Daten wie Paketverluste, Jitter und Roundtripzeiten. Anhand dieser Informationen lässt sich erkennen, was mit dem Anruf zwischen dem Verlassen des einen Benutzerendpunkts und dem Eintreffen am anderen Benutzerendpunkt passiert.

  - **Probleme, die dem Endbenutzer gemeldet werden** . Diese Metriken beinhalten Benachrichtigungen bezüglich schlechter Qualität, die Lync 2013 Endbenutzern bereitstellt. Gründe hierfür können ein zu großer Abstand zum Mikrofon, zu leises Sprechen, eine mangelhafte Netzwerkverbindung oder unzureichende Ressourcen aufgrund der Netzwerkauslastung durch ein anderes Programm sein.

  - **Umgebungsinformationen** . Diese Metriken erfassen detaillierte Faktoren der Anrufqualität wie den Typ des verwendeten Mikrofons und Lautsprechers, Angaben darüber, ob eine VPN-Verbindung verwendet wurde und Angaben darüber, ob eine WLAN-Verbindung verwendet wurde.

Am Ende jedes Anrufs übertragen SIP-kompatible Endpunkte diese Informationen automatisch an den Front-End-Server, von dem der Anruf bereitgestellt wurde. Sie müssen nichts tun, damit diese Informationen von den Endpunkten übertragen werden. Das SIP-Protokoll ist bereits entsprechend konfiguriert. Wenn Sie diese Informationen jedoch erfassen und speichern möchten, müssen Sie die Überwachung aktivieren. Wenn Sie die Überwachung installieren und aktivieren, werden die Anrufinformationen von den Agents gesammelt, die auf dem Front-End-Server ausgeführt werden, und an ein SQL Server-Datenbankpaar weitergeleitet.

Das Installieren und Konfigurieren der Überwachung wurde in Lync Server 2013 vereinfacht. In früheren Versionen der Software war noch eine separate Monitoring Server-Rolle für die Überwachung erforderlich, und ein separater Computer musste als Monitoring Server bereitgestellt werden. In Lync Server 2013 ist dagegen keine separate Monitoring Server-Rolle mehr erforderlich. Stattdessen wurde der Überwachungsdienst (in Form von einheitlichen Datenerfassungs-Agents) auf allen Front-End-Servern integriert. Dies hat zwei wesentliche Vorteile:

  - Verringerung der Anzahl erforderlicher Serverrollen zur Implementierung von Lync Server 2013. Weniger Monitoring Server-Rollen bedeuten gleichzeitig weniger Kosten, da weniger dedizierte Server für die Überwachung unterhalten werden müssen.

  - Einfacheres Setup und einfachere Verwaltung von Lync Server 2013. Durch das Platzieren der Überwachungsdienste auf den einzelnen Front-End-Servern entfällt die Notwendigkeit der Installation, Konfiguration und Verwaltung von Monitoring Server-Rollen.

Weitere Informationen finden Sie im Bereitstellungshandbuch von Lync Server 2013 im Thema [Bereitstellen des Monitoring Servers](lync-server-2013-deploying-monitoring.md).

