#!/usr/bin/env bash

if [ $# -ne 2 ]; then
  >&2 echo "Usage: $0 <author> <commit>"
  exit 1
fi

AUTHOR=$1
AUTHOR_NAME=$(echo $AUTHOR | perl -wlne '/^(.*?)\s*<.*>$/ and print $1')
AUTHOR_EMAIL=$(echo $AUTHOR | perl -wlne '/^.*\s*<(.*)>$/ and print $1')
COMMIT=$(git rev-parse --short $2)

{
  GIT_SEQUENCE_EDITOR="sed -i -e 's/^pick $COMMIT/edit $COMMIT/'" git rebase -i $COMMIT~1^^ 
  GIT_COMMITTER_NAME="$AUTHOR_NAME" GIT_COMMITTER_EMAIL="$AUTHOR_EMAIL" git commit --amend --no-edit --author="$AUTHOR"
  git rebase --continue
} &> /dev/null

echo "$AUTHOR_NAME is now the author of $COMMIT. You're officially an asshole.";
