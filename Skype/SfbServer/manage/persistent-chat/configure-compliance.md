---
title: Konfigurieren des Kompatibilitätsdiensts für den Server für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 24e36ea3-fb8a-45a4-b6b7-38c2e256b218
description: 'Zusammenfassung: Erfahren Sie, wie Sie den Kompatibilitätsdienst für den Server für beständigen Chat in Skype for Business Server 2015 konfigurieren.'
ms.openlocfilehash: ee7dbc3ad8e7eedcadcc60850e35b753c5fadb43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815065"
---
# <a name="configure-the-compliance-service-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Konfigurieren des Kompatibilitätsdiensts für den Server für beständigen Chat in Skype for Business Server 2015

**Zusammenfassung:** Erfahren Sie, wie Sie den Kompatibilitätsdienst für den Server für beständigen Chat in Skype for Business Server 2015 konfigurieren.

Mit der Kompatibilität für beständigen Chat können Administratoren ein Archiv von Nachrichten und Aktivitäten für beständigen Chat verwalten. Der Kompatibilitätsdienst zeichnet Daten im Zusammenhang mit jeder Unterhaltung des Servers für beständigen Chat auf und archiviert sie, z. B. wenn ein Teilnehmer:

- Beitritt zu einem Chatroom für beständigen Chat

- Verlässt einen Chatroom

- Veröffentlicht eine Nachricht

- Ansichten des Chatverlaufs

- Lädt eine Datei hoch

- Lädt eine Datei herunter

Diese Informationen können nach Bedarf aus der Kompatibilitätsdatenbank SQL abgerufen werden. 

> [!NOTE]
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter ["Erste Schritte mit Ihrem Microsoft Teams-Upgrade".](/microsoftteams/upgrade-start-here) Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität benötigen, zu Teams migrieren oder Weiterhin Skype for Business Server 2015 verwenden. 

## <a name="configure-the-compliance-service-by-using-windows-powershell"></a>Konfigurieren des Kompatibilitätsdiensts mithilfe Windows PowerShell

Nachdem der Kompatibilitätsdienst mithilfe des Topologie-Generators aktiviert wurde, können Sie den Dienst mithilfe des Cmdlets **"Set-CsPersistenChatComplianceConfiguration"** konfigurieren:

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>
```

oder

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>
```

Sie können die folgenden Parameter festlegen:

- AdapterType : Ermöglicht die Angabe des Adaptertyps. Ein Adapter ist ein Drittanbieterprodukt, das die Daten in der Kompatibilitätsdatenbank in ein bestimmtes Format konvertiert. XML ist die Standardeinstellung.

- OneChatRoomPerOutputFile : Mit diesem Parameter können Sie angeben, dass für jeden Chatroom separate Berichte erstellt werden sollen.

- AddChatRoomDetails: Bei Aktivierung zeichnet dieser Parameter zusätzliche Details zu jedem Chatroom in der Datenbank auf. Da diese Einstellung die Größe der Datenbank erheblich erhöhen kann, ist sie standardmäßig deaktiviert.

- AddUserDetails: Bei Aktivierung zeichnet dieser Parameter zusätzliche Details zu jedem Chatroombenutzer in der Datenbank auf. Da diese Einstellung die Größe der Datenbank erheblich erhöhen kann, ist sie standardmäßig deaktiviert.

- Identität : Dieser Parameter ermöglicht den Bereich der Kompatibilitätseinstellungen für eine bestimmte Auflistung, einschließlich der globalen, Standort- und Dienstebenen. Der Standardwert ist die globale Ebene. 

- RunInterval – Dieser Parameter bestimmt die Zeit, bevor der Server die nächste Konformitätsausgabedatei erstellt (der Standardwert beträgt 15 Minuten).

## <a name="use-a-customized-compliance-adapter"></a>Verwenden eines angepassten Kompatibilitätsadapters

Sie können einen benutzerdefinierten Adapter schreiben, anstatt den mit dem Server für beständigen Chat installierten XmlAdapter zu verwenden. Hierzu müssen Sie eine .NET Framework-Assembly bereitstellen, die eine öffentliche Klasse enthält, die die **IComplianceAdapter**-Schnittstelle implementiert. Sie müssen diese Assembly im Installationsordner für den Server für beständigen Chat auf jedem Server in Ihrem Pool für den Server für beständigen Chat platzieren. Jeder der Konformitätsserver kann Konformitätsdaten für Ihren Adapter bereitstellen, aber die Konformitätsserver stellen keine doppelten Konformitätsdaten für mehrere Instanzen des Adapters bereit.

Die Schnittstelle wird in der Compliance.dll im Namespace  `Microsoft.Rtc.Internal.Chat.Server.Compliance` definiert. Die Schnittstelle definiert zwei Methoden, die ihr benutzerdefinierter Adapter implementieren muss.

Der Kompatibilitätsserver für beständigen Chat wird beim ersten Laden des Adapters die folgende Methode aufrufen. Die enthält die Konformitätskonfiguration für den beständigen  `AdapterConfig` Chat, die für den Kompatibilitätsadapter relevant ist:

```cpp
void SetConfig(AdapterConfig config)
```

Der Kompatibilitätsserver für beständigen Chat ruft die folgende Methode in regelmäßigen Abständen auf, solange neue zu übersetzende Daten vorhanden sind. Dieses Zeitintervall entspricht dem in der Konformitätskonfiguration für beständigen  `RunInterval` Chat festgelegten Intervall:

```cpp
void Translate(ConversationCollection conversations)
```

Die  `ConversationCollection` enthält die Unterhaltungsinformationen, die beim letzten Aufgerufen dieser Methode gesammelt wurden.

## <a name="customize-the-xslt-definition-file"></a>Anpassen der XSLT-Definitionsdatei

Die Kompatibilitätsdaten werden als XML übermittelt, das Sie mithilfe einer XSLT-Definitionsdatei in das format umwandeln können, das ihrer Organisation am besten entspricht. In diesem Thema ist die vom Kompatibilitätsdienst erstellte XML-Datei beschrieben. Zudem werden Beispiele von XSLT-Definition und Ausgabedateien bereitgestellt.

### <a name="output-format"></a>OutputFormat

Die Ausgabe des Kompatibilitätsdiensts wird nach Unterhaltung (unterhaltungselement) und dann nach Nachricht (dem Nachrichtenelement) kategorisiert, wie im folgenden Codebeispiel gezeigt:

```XML
<?xml version="1.0" encoding="utf-8" ?> 
<Conversations xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Conversation>
    <Channel uri="ma-chan://litwareinc.com/300" name="ma-chan://litwareinc.com/300" islogged="" /> 
    <!--FirstMessage goes here --!>
    <Messages> 
      <!—Messages go here--!>
    </Messages>
    <StartTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
    <EndTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
  </Conversation>
</Conversations>
```

Ein Unterhaltungselement enthält vier Elemente ("Channel", "FirstMessage", "StartTimeUTC" und "EndTimeUTC"). Das Element "Channel" enthält den Uniform Resource Identifier (URI) des Chatrooms, und das Element "FirstMessage" beschreibt das erste Element im Nachrichtenelement. Die Elemente "StartTimeUTC" und "EndTimeUTC" geben die Start- und Endzeiten für die Unterhaltung an, wie im folgenden Codebeispiel gezeigt:

```xml
<FirstMessage type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
</FirstMessage>
```

Ein Nachrichtenelement enthält zwei Elemente ("Sender" und "DateTimeUTC") und drei Attribute ("Type", "Content" und "ID"). Das Sender -Element stellt den Benutzer, der die Nachricht sendet, und das DateTimeUTC -Element darstellt, wenn ein Ereignis auftritt, wie im folgenden Codebeispiel gezeigt:

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message>
```

In der folgenden Tabelle werden die Nachrichtenattribute "Type", "Content" und "ID" beschrieben.

**Nachrichtenelementattribute**

|**Attribut**|**Beschreibung**|**Optional/Erforderlich**|
|:-----|:-----|:-----|
|Typ  <br/> |Gibt den Nachrichtentyp an. Die Nachrichtentypen sind in der Tabelle "Nachrichtenelemente – Nachrichtentypen" beschrieben.  <br/> |Erforderlich  <br/> |
|Inhalt  <br/> |Enthält den Inhalt der Nachricht. Nachrichten vom Typ "Join" oder "Part" verwenden dieses Attribut nicht.  <br/> |Optional  <br/> |
|ID  <br/> |Gibt die eindeutige ID des Inhalts an. Dieses Attribut wird nur mit Nachrichten vom Typ "Chat" verwendet.  <br/> |Optional  <br/> |

Jedes "Sender"-Element enthält fünf Attribute: "user name", "ID", "email", "internal" und "URI". Diese Attribute sind in der folgenden Tabelle beschrieben.

**"Sender"-Elementattribute**

|**Attribut**|**Beschreibung**|**Optional/Erforderlich**|
|:-----|:-----|:-----|
|Username  <br/> |Der Name des Absenders.  <br/> |Optional  <br/> |
|ID  <br/> |Die eindeutige ID des Absenders.  <br/> |Erforderlich  <br/> |
|E-Mails  <br/> |Die E-Mail-Adresse des Absenders.  <br/> |Optional  <br/> |
|Intern  <br/> |Gibt an, ob es sich um einen internen Benutzer oder einen Verbundbenutzer handelt. Bei Festlegung des Werts auf "true"  (wahr) ist der Benutzer intern.  <br/> |Optional  <br/> |
|Uri  <br/> |Der SIP-URI des Benutzers.  <br/> |Erforderlich  <br/> |

Die folgenden Beispiele zeigen die Nachrichtentypen, die das Nachrichtenelement enthalten kann. Sie enthält auch Beispiele für die Verwendung der einzelnen Elemente.

Teilnehmen – Ein Benutzer tritt einem Chatroom bei.

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message
```

Teil : Ein Benutzer verlässt einen Chatroom.

```xml
<Message type="PART" content="" id="0">
  < Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
</Message>
```

Chat : Die E-Mail-Adresse des Absenders.

```xml
<Message type="CHAT" content="hello" id="1">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351800522" string="2008-03-12T19:56:40.522264Z" long="633409486005222640" /> 
</Message>
```

Backchat : Ein Benutzer fordert Inhalte aus dem Chatverlauf an.

```xml
<Message type="BACKCHAT" content="backchatcontent" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206034385284" string="2008-03-20T17:33:05.2841594Z" long="633416311852841594" /> 
</Message>
```

Dateiupload: Ein Benutzer lädt eine Datei hoch.

```xml
<Message type="FILEUPLOAD" content="0988239a-bb66-4616-90a4-b07771a2097c.txt" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351828975" string="2008-03-12T19:57:08.9755711Z" long="633409486289755711" /> 
</Message>
```

Dateidownload: Ein Benutzer lädt eine Datei herunter.

```xml
<Message type="FILEDOWNLOAD" content="006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt" id="0">
  <Sender UserName="kazuto@litwareinc.com" id="10" email="" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212611141851" string="2008-06-04T20:25:41.8518646Z" long="633482079418518646" /> 
</Message>
```

### <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a>XSD der Standardausgabe für beständigen Chat und Beispiel-XSL-Transformation

Das folgende Codebeispiel enthält die Standardausgabe des Kompatibilitätsservers:

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="Conversations" xmlns="" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">
   <xs:simpleType name="ComplianceMessageType">
      <xs:restriction base="xs:string">
        <xs:enumeration value="JOIN"/>
        <xs:enumeration value="PART"/>
        <xs:enumeration value="CHAT"/>
        <xs:enumeration value="BACKCHAT"/>
        <xs:enumeration value="FILEUPLOAD"/>
        <xs:enumeration value="FILEDOWNLOAD"/>
      </xs:restriction>
    </xs:simpleType>

  <xs:element name="Sender">
    <xs:complexType>
      <xs:attribute name="UserName" type="xs:string" />
      <xs:attribute name="id" type="xs:int" />
      <xs:attribute name="email" type="xs:string" use="optional" />
      <xs:attribute name="internal" type="xs:boolean" use="optional" >
        <xs:annotation><xs:documentation>If the user is internal or federated</xs:documentation></xs:annotation>
      </xs:attribute>
      <xs:attribute name="uri" type="xs:anyURI" use="optional" />
    </xs:complexType>
  </xs:element>
  <xs:element name="DateTimeUTC">
    <xs:complexType>
      <xs:attribute name="since1970" type="xs:long" />
      <xs:attribute name="string" type="xs:string" />
      <xs:attribute name="long" type="xs:long" />
    </xs:complexType>
  </xs:element>
  <xs:element name="Conversations" msdata:IsDataSet="true" msdata:UseCurrentLocale="true">
    <xs:complexType>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element ref="Sender" />
        <xs:element ref="DateTimeUTC" />
        <xs:element name="Conversation">
          <xs:complexType>
            <xs:sequence>
              <xs:element name="Channel" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="uri" type="xs:anyURI" />
                  <xs:attribute name="name" type="xs:string" use="optional" />
                </xs:complexType>
              </xs:element>
              <xs:element name="FirstMessage" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                    <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                  </xs:sequence>
                  <xs:attribute name="type" type="ComplianceMessageType" />
                  <xs:attribute name="content" type="xs:string" />
                  <xs:attribute name="id" type="xs:int" />
                </xs:complexType>
              </xs:element>
              <xs:element name="Messages" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element name="Message" minOccurs="0" maxOccurs="unbounded">
                      <xs:complexType>
                        <xs:sequence>
                          <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                          <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                        </xs:sequence>
                        <xs:attribute name="type" type="ComplianceMessageType" />
                        <xs:attribute name="content" type="xs:string" />
                        <xs:attribute name="id" type="xs:int" />
                      </xs:complexType>
                    </xs:element>
                  </xs:sequence>
                </xs:complexType>
              </xs:element>
              <xs:element name="StartTimeUTC" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="since1970" type="xs:long" />
                  <xs:attribute name="string" type="xs:string" />
                  <xs:attribute name="long" type="xs:long" />
                </xs:complexType>
              </xs:element>
              <xs:element name="EndTimeUTC" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="since1970" type="xs:long" />
                  <xs:attribute name="string" type="xs:string" />
                  <xs:attribute name="long" type="xs:long" />
                </xs:complexType>
              </xs:element>
            </xs:sequence>
          </xs:complexType>
        </xs:element>
      </xs:choice>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

Das folgende Codebeispiel enthält eine BEISPIEL-XSL-Transformation:

```xml
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xs="http://www.w3.org/2001/XMLSchema" exclude-result-prefixes="xs">
   <xsl:output method="xml" encoding="UTF-8" indent="yes" />

   <xsl:template match="/">
      <FileDump>
         <xsl:apply-templates />
      </FileDump>
   </xsl:template>

   <xsl:template match="Conversation">
      <xsl:variable name="chanName" select="Channel/@name" />
      <Conversation Perspective="{$chanName}_group_channel">
         <RoomID><xsl:value-of select="Channel/@name" /></RoomID>
         <StartTimeUTC><xsl:value-of select="StartTimeUTC/@since1970" /></StartTimeUTC>
         <xsl:apply-templates />
         <EndTimeUTC><xsl:value-of select="EndTimeUTC/@since1970" /></EndTimeUTC>
      </Conversation>
   </xsl:template>

   <xsl:template match="Message">
      <xsl:choose>
         <xsl:when test="@type='JOIN'">
            <ParticipantEntered>
               <xsl:call-template name="DateTimeAndLogin" />
               <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
               <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
               <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
            </ParticipantEntered>
         </xsl:when>

         <xsl:when test="@type='PART'">
            <ParticipantLeft>
               <xsl:call-template name="DateTimeAndLogin" />
               <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
               <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
               <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
            </ParticipantLeft>
         </xsl:when>

         <xsl:when test="@type='FILEUPLOAD' or @type='FILEDOWNLOAD'">
            <FileTransferStarted>
               <xsl:call-template name="DateTimeAndLogin" />
               <FileName><xsl:value-of select="@content" /></FileName>
            </FileTransferStarted>
            <FileTransferEnded>
               <xsl:call-template name="DateTimeAndLogin" />
               <FileName><xsl:value-of select="@content" /></FileName>
               <Status>Completed</Status>
            </FileTransferEnded>
         </xsl:when>

         <xsl:when test="@type='CHAT' or @type='BACKCHAT'">
            <Message>
               <xsl:call-template name="DateTimeAndLogin" />
               <Content><xsl:value-of select="@content" /></Content>
            </Message>
         </xsl:when>

         <xsl:otherwise />
      </xsl:choose>
   </xsl:template>

   <xsl:template name="DateTimeAndLogin">
      <LoginName><xsl:value-of select="Sender/@userName" /></LoginName>
      <DateTimeUTC><xsl:value-of select="DateTimeUTC/@since1970" /></DateTimeUTC>
   </xsl:template>
</xsl:stylesheet>
```
