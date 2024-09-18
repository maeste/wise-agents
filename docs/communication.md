# Comunication between agents



# Wise Agent Message Schema

This schema represents the structure of a `WiseAgentMessage` object in the Wise Agents system. It includes details about the message content, the sender, the context, and related metadata.

```yaml
schema:
  WiseAgentMessage:
    description: |
      A message object in the Wise Agent system that includes details about the message content,
      the sender, the context, and any related metadata.
    properties:
      _chat_id:
        type: string
        description: |
          (Optional) The unique identifier for the chat session associated with this message.
        required: false
      _context_name:
        type: string
        description: |
          (Optional) The context in which this message is being exchanged (e.g., "Weather").
        required: false
      _message:
        type: string
        description: |
          (Required) The content of the message being sent.
        required: true
      _message_type:
        type: integer
        description: |
          (Optional) The type of the message, represented as an integer.
        enum:
          - 1  # Add other message types here as needed
        required: false
      _route_response_to:
        type: string
        description: |
          (Optional) The name of the agent to route the response to (e.g., "Agent1").
        required: false
      _sender:
        type: string
        description: |
          (Optional) The agent that is sending this message.
        required: false
      _tool_id:
        type: string
        description: |
          (Optional) The identifier of the tool or agent responsible for handling this message (e.g., "WeatherAgent").
        required: false

```

## Properties

### `_chat_id`
- **Type**: `string`
- **Description**: 
  (Optional) The unique identifier for the chat session associated with this message.

### `_context_name`
- **Type**: `string`
- **Description**: 
  (Optional) The context in which this message is being exchanged (e.g., "Weather").

### `_message`
- **Type**: `string`
- **Description**: 
  (Required) The content of the message being sent.

### `_message_type`
- **Type**: `integer`
- **Description**: 
  (Optional) The type of the message, represented as an integer.
  
  **Enum**: 
  - `1`  (Additional message types can be added as needed.)

### `_route_response_to`
- **Type**: `string`
- **Description**: 
  (Optional) The name of the agent to route the response to (e.g., "Agent1").

### `_sender`
- **Type**: `string`
- **Description**: 
  (Optional) he agent that is sending this message.

### `_tool_id`
- **Type**: `string`
- **Description**: 
  (Optional) The identifier of the tool or agent responsible for handling this message (e.g., "WeatherAgent").

## YAML Example of a valid message

```yaml
!wiseagents.WiseAgentMessage
_chat_id: '12345'
_context_name: Weather
_message: Hello
_message_type: !!python/object/apply:wiseagents.wise_agent_messaging.WiseAgentMessageType
- 1
_route_response_to: Agent1
_sender: Agent1
_tool_id: WeatherAgent
```

This example demonstrates how a `WiseAgentMessage` can be structured using the provided schema. The YAML example includes essential details such as the chat ID, context, message content, sender, and tool identifier.