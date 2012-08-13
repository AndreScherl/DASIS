Andre Scherl
dasis@andrescherl.de


ABOUT
*****
DASIS is a package of Moodle[1] extensions to support students in making their individual way through hypermedia learning contents.

Main features are:
 - concept map-based navigation between courses
 - direct guidance navigation with learning paths
 - adaptive navigation support

DASIS contains three essential elements:
 1. Block “Navigation Web”
 2. Block “Learner Preferences”
 3. Block “Learner Adaptation”

Semantic Web is necessary for interdisciplinary navigation and works without adaptation but can be enhanced with adaptive navigation support. Adaptation is realized by the blocks Learner Adaptation and Learner Preferences. Both blocks were originally developed by Gert Sauerstein[2]. They were ported to Moodle 2.0+ and fitted to the needs of DASIS.

We used the module "Decision Tree" (mod/decisiontree) to create and provide learning style questionnaires. This is not necessary to use the features of DASIS. It is no assessment ready to use because all the questions have to be entered first.


INSTALLATION
************
 1. Download the files
 2. Unzip the package if necessary
 3. Copy the directories “semantic_web”, “user_preferences”, and “case_repository” into the directory “blocks” of your moodle directory
 4. Paste the following lines of code at the end of the file /admin/settings/plugins.php
/**
 * Settings for block user_preferences via external page
 *
 * @package	DASIS, Andre Scherl 
 */
if ($hassiteconfig) {
	$ADMIN->add('blocksettings', new admin_externalpage('dasis_user_preferences', get_string('pluginname', 'block_user_preferences'), $CFG->wwwroot.'/blocks/user_preferences/global_config.php'));
	$ADMIN->add('blocksettings', new admin_externalpage('dasis_case_repository', get_string('pluginname', 'block_case_repository'), $CFG->wwwroot.'/blocks/case_repository/settings_case_repository.php'));
}
 5. Go to your Moodle site and choose “Messages” within the administration menu. The plugin installation process should start.
 6. If installation is finished, navigate to Plugins ⇒ Blocks ⇒ Learner Preferences to trigger final settings. After the page loaded completely, the installation is complete.


MORE INFO & USER MANUAL
***********************
More information can be found in the user manual (dasis.pdf) within this package.


[1]	“About Moodle,” docs.moodle.org. [Online]. Available: http://docs.moodle.org/22/en/About_Moodle. [Accessed: 14-Mar.-2012].
[2]	G. Sauerstein, KI-Ansätze zur Lerner-Adaption in Lern-Management-Systemen, 2007.
