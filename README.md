[Adding your own commands](DEVELOPING.md#custom-commands)

[Adding your own event handlers](DEVELOPING.md#custom-event-handlers)

[Adding your own storage file](DEVELOPING.md#custom-storage-file)


## Command Info

- Default prefix: `!`
- `<argument>` = **Required argument**
- `[argument]` = **Optional argument**

## Commands

- `!mod <add|remove|list> <role ID>`
  - Adds, removes the role ID to the list of moderator roles.
  - If you want to `list` the roles, you do not need the role ID at the end.

- `!mute <user ID> [reason]`
  - Permanently mutes the user. Must be unmuted manually.

- `!tempmute <user ID> <duration> [reason]`
  - Temporarily mutes the user.

- `!unmute <user ID>`
  - Unmutes the user

- `!ban <user ID> <duration> <reason>`
  - Bans the user from the server for the duration specified
  - Reason is required. If you do not have a reason, you should not be banning them.

- `!unban <user ID>`
  - Unbans the user from the server.

- `!reload`
  - Reloads the command registry for any changes that were made to commands

- `!reload events`
  - Reloads the event registry for any changes that were made

## Issues with custom commands?

Ensure that:
- Your command is a subclass of the base command class. (use `from commands.base import Command` and then define the class like this: `class MyCommand(Command):` so it is a subclass of it)
- It has an `async def execute(self, message, **kwargs):` function to execute the command
- It doesn't have basic python syntax errors.
