---
title: Konfigurieren des Vermittlungsservers
TOCTitle: Konfigurieren des Vermittlungsservers
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204913(v=OCS.15)
ms:contentKeyID: 49294066
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren des Vermittlungsservers

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

In diesem Verfahren werden die Schritte ausgeführt, die erforderlich sind, um den Lync Server 2013-Pool für die Verwendung mit dem Lync Server 2013-Vermittlungsserver anstatt mit dem Office Communications Server 2007 R2-Vermittlungsserver der Vorversion zu konfigurieren.

Für eine erfolgreiche Veröffentlichung, Aktivierung oder Deaktivierung einer Topologie beim Hinzufügen oder Entfernen einer Serverrolle müssen Sie als Mitglied der Gruppen "RTCUniversalServerAdmins" und "Domänen-Admins" angemeldet sein. Es ist auch möglich, die geeigneten Administratorrechte und -berechtigungen für das Hinzufügen von Serverrollen zu delegieren. Ausführliche Informationen finden Sie unter Delegieren von Setupberechtigungen in der Bereitstellungsdokumentation für Standard Edition-Server oder Enterprise Edition-Server. Für andere Konfigurationsänderungen müssen Sie lediglich Mitglied der Gruppe "RTCUniversalServerAdmins" sein.


> [!NOTE]
> Aktuelle Informationen über das Auffinden von qualifizierten PSTN-Gateways, IP-PBXs und SIP-Trunking-Diensten, die mit Lync Server 2013 ausgeführt werden können, finden Sie auf der Website "Microsoft Unified Communications Open Interoperability Program" unter <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>.



## So konfigurieren Sie den Vermittlungsserver mithilfe des Topologie-Generators

1.  Öffen Sie über den Topologie-Generator eine vorhandene Topologie.

2.  Navigieren Sie im linken Bereich zu **PSTN-Gateways** .

3.  Klicken Sie mit der rechten Maustaste auf **PSTN-Gateways** , und klicken Sie dann auf **Neues IP/PSTN-Gateway** .

4.  Geben Sie auf der Seite **Neues IP/PSTN-Gateway definieren** die folgenden Informationen ein:
    
      - Geben Sie einen vollqualifizierten Domänennamen oder eine IP-Adresse für das Gateway ein. Der FQDN des Gateways ist notwendig, wenn das Gateway das TLS-Protokoll verwendet.
    
      - Übernehmen Sie den Standardwert von **Überwachungsport für das IP/PSTN-Gateway** , oder geben Sie den neuen Überwachungsport ein, falls er geändert wurde.
    
      - Legen Sie das **SIP-Transportprotokoll** fest.

5.  Navigieren Sie im linken Bereich zum **Front-End-Pool der Enterprise Edition** oder zum **Standard Edition-Server** .

6.  Klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie auf **Eigenschaften bearbeiten** .

7.  Legen Sie unter **Vermittlungsserver** die **Überwachungsports** fest.

8.  Ordnen Sie dann das neu erstellte PSTN-Gateway zu, indem Sie es markieren und auf **Hinzufügen** klicken.

9.  Wählen Sie im **Topologie-Generator** den obersten Knoten **Lync Server** aus.

10. Wählen Sie im Menü **Aktion** den Eintrag **Topologie veröffentlichen** aus, und klicken Sie auf **Weiter** .

11. Wenn der **Veröffentlichungs-Assistent** abgeschlossen ist, klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.


> [!NOTE]
> Die Durchführung der Schritte im nächsten Thema <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Ändern der VoIP-Routen für die Verwendung des neuen Lync Server 2013-Vermittlungsservers</A> ist wichtig, um sicherzustellen, dass die VoIP-Routen auf den richtigen Vermittlungsserver zeigen.


