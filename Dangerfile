declared_trivial = github.pr_title.include? "[TRIVIAL]"

message "Thank you so much for your work here @#{github.pr_author} 🎉
  You might find a few suggestions from me for this Pull Request below 🙂"

pr_title_regex = /^(Added|Changed|Deprecated|Removed|Fixed|Security)\:\s\[([A-Z0-9]+)\-([0-9]+)\]\s(.*)$/
if !github.pr_title.match(pr_title_regex) && !declared_trivial
  fail "Please provide a Pull Request title conforming to the pattern:
    `Type: [TEAM-1234] Descrição da mudança em português`
    Possible `Type`s are `Added`, `Changed`, `Deprecated`, `Removed`, `Fixed` or `Security`."
end

if github.pr_title.include? "[WIP]"
  fail "I noticed this is marked as Work In Progress, does it need to be open before it is ready? 🤔
    Maybe try opening a Draft Pull Request next time."
end

if github.pr_body.length < 5
  warn "You should provide a summary in the Pull Request description so that the reviewer has more context on this Pull Request 💚"
end

if git.lines_of_code > 500
  warn "This Pull Request is quite a big one! Maybe try splitting this into separate tasks next time 😅"
end
