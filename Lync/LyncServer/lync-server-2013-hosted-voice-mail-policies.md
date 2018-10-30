---
title: 'Lync Server 2013: Richtlinien für gehostete Voicemail'
TOCTitle: Richtlinien für gehostete Voicemail
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398932(v=OCS.15)
ms:contentKeyID: 49295542
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Richtlinien für gehostete Voicemail in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Eine *Richtlinie für gehostete Voicemail* stellt der Lync Server 2013 ExUM-Routinganwendung Informationen zum Routing von Anrufen für Benutzer bereit, deren Postfächer über einen gehosteten Exchange-Dienst verwaltet werden.


> [!NOTE]
> Richtlinien für gehostete Voicemail sind nur für die Integration von Lync Server 2013 in gehostete Exchange UM-Dienste erforderlich. Für die Integration in lokale Exchange UM-Dienste werden die Richtlinien nicht benötigt.



## Bereich einer Richtlinie für gehostete Voicemail

Der Bereich einer Richtlinie für gehostete Voicemail bestimmt die Hierarchieebene, auf der die Richtlinie angewendet wird. Sie können Richtlinien für gehostete Voicemail mit folgenden Bereichsebenen konfigurieren:

  - Die *globale* Richtlinie kann sich potenziell auf alle Benutzer in der Lync Server 2013-Bereitstellung auswirken. Wenn ein Benutzer für den Zugriff auf gehostete Exchange UM-Dienste aktiviert ist, ihm jedoch keine Benutzerrichtlinie und dem Standort des Benutzers keine Standortrichtlinie zugewiesen wurde, wird die globale Richtlinie angewendet. Die globale Richtlinie wird mit Lync Server 2013 installiert. Sie können diese Richtlinie Ihren Anforderungen entsprechend ändern, Sie können sie jedoch weder umbenennen noch löschen.

  - Eine *Standortrichtlinie* kann sich auf alle Benutzer auswirken, die an dem Standort verwaltet werden, für den die Richtlinie definiert wurde. Wenn ein Benutzer für den Zugriff auf gehostete Exchange UM-Dienste konfiguriert ist, ihm jedoch keine Benutzerrichtlinie zugewiesen wurde, findet die Standortrichtlinie Anwendung.

  - Eine *Benutzerrichtlinie* kann sich nur auf einzelne Benutzer oder Benutzergruppen auswirken. Zum Erzwingen einer Richtlinie auf Benutzerebene müssen Sie die Richtlinie explizit auf einzelne Benutzer, Gruppen oder Kontaktobjekte anwenden.


> [!NOTE]
> In den meisten Fällen ist nur eine Richtlinie für gehostete Voicemail erforderlich. Häufig können Sie die globale Richtlinie ändern, um alle Anforderungen zu erfüllen. Wenn Sie mehrere Richtlinien für gehostete Voicemail bereitstellen, gelten alle diese Richtlinien auf Benutzerebene.



## Attribute einer Richtlinie für gehostete Voicemail

In einer Richtlinie für gehostete Voicemail sind zwei Attribute definiert, welche die ExUM-Routinganwendung von Lync Server 2013 in den Anforderungs-URI einer INVITE-Nachricht einfügt, die an die Implementierung der gehosteten Exchange UM-Dienste gesendet wird:

  - **Destination :** Der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des gehosteten Exchange UM-Diensts. Dieser Wert wird vom lokalen Lync Server-Edgeserver zu Routingzwecken verwendet.
    

    > [!NOTE]
    > Der FQDN für Exchange Online ist exap.um.outlook.com .



  - **Organization :** Der FQDN des Mandanten im gehosteten Exchange UM-Dienst, der die Postfächer Ihrer Lync Server 2013-Benutzer verwaltet. Eine Voicemailrichtlinie kann mehrere Organisationen umfassen. Wenn die Richtlinie für mehr als eine Organisation gilt, muss dieses Attribut eine durch Trennzeichen getrennte Liste der Exchange Server-Mandanten enthalten, welche die Postfächer Ihrer Lync Server 2013-Benutzer verwalten.


> [!NOTE]
> Der Administrator für Mandanten Ihres gehosteten Exchange UM-Diensts stellt die erforderlichen Werte für die Einstellungen der Attribute "Destination" und "Organization" bereit. Zum Erstellen und Konfigurieren einer neuen Richtlinie müssen Sie das Cmdlet "New-CsHostedVoicemailPolicy" ausführen. Wenn Sie eine vorhandene Richtlinie (z.&nbsp;B. die globale Richtlinie) ändern möchten, verwenden Sie das Cmdlet "Set-CsHostedVoicemailPolicy".



Ausführliche Informationen zum Verwalten von Richtlinien für gehostete Voicemail finden Sie in der Lync Server-Verwaltungsshell-Dokumentation zu den folgenden Cmdlets:

  - New-CsHostedVoicemailPolicy

  - Set-CsHostedVoicemailPolicy

  - Get-CsHostedVoicemailPolicy

## Zuweisen von Richtlinien auf Benutzerebene

Wenn Ihre Richtlinien für gehostete Voicemail auf Benutzerebene definiert sind, müssen Sie diese explizit zuweisen. Sie können das Cmdlet "Grant-CsHostedVoicemailPolicy" ausführen, um die Richtlinie einzelnen Benutzern oder Gruppen zuzuweisen.

Ausführliche Informationen zum Zuweisen einer Richtlinie für gehostete Voicemail auf Benutzerebene und zum Entfernen einer solchen Zuweisung finden Sie in der Lync Server-Verwaltungsshell-Dokumentation für die folgenden Cmdlets:

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

