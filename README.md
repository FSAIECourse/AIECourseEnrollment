# AIE Course Enrollment

Creates one private student repository from `FSAIECourse/Artificial_Intelligence_Ecosystem`, named `aie-<cohort>-<GitHub username>`.

## Administrator setup

1. Keep Issues and GitHub Actions enabled.
2. Install an enrollment GitHub App in FSAIECourse. Grant repository Administration and Contents read/write, Issues read/write, and Metadata read access. If the template contains Actions workflows, grant Workflows write access too.
3. The installation must access the enrollment repository, the template, and repositories created by the bot. For this dedicated course organization, all-repository access is the simplest configuration.
4. Add Actions repository secrets `APP_ID` and `APP_PRIVATE_KEY` using the app ID and generated PEM private key. Never commit the key.
5. Set `PREFIX`, `MONTHLY_CODE` (SHA-256 of the exact claim code, with no newline), and `MAX_REPOS` in `pg2Info.txt`. MAX_REPOS is the number of student repositories allowed for that cohort.
6. Submit one enrollment request and inspect the Actions run before inviting the class.

The copied cohort settings have not been changed. Confirm the claim code and cohort before enrollment. Claim codes entered in public issues are publicly visible; they are a shared class gate, not proof of student identity.

The workflow runs when an issue receives the `provision-repo` label, which the enrollment form applies. Existing student repositories are skipped on repeat requests. Students must accept their repository invitations.

The older setup.md, teacher.md, and theProcess.md documents were inherited from another course and may contain outdated organization and repository references. Use this README for the AIE configuration.
