file_lib
======================
�t�@�C������Ɋ֘A����N���X�A�֐����쐬���܂���
�����p�͎��ȐӔC�ł����R�ɂǂ���

�g����
------
�P�Dpip�R�}���h�����s���A���W���[�����_�E�����[�h���Ă�������

    pip install file_lib

�Q�D�N���X���C���|�[�g���A���L��̗p�Ɏg�p���Ă�������

    from file_lib.csv_file import CsvFileReader
    reader = CsvFileReader(/tmp/item_list.csv)
    for line in reader.read_file()
        print ','.join(line)

    from file_lib.file_utils import get_file_lines
    for line in get_file_lines(/tmp/item_list.csv)
        print line

�@�\�Љ�
------
### CsvFileReader
#### CSV�t�@�C���Ǎ��@�\��ێ������N���X�ł��A�}���`�o�C�g�����ɂ��Ή����Ă��܂��B
***
__init__(file_path, encode='utf-8', quote='"', delimiter=',', line_feed='\r\n', skip_initial_space=False):

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| file_path | �� | �ǂݍ��݂���CSV�̃t�@�C���p�X | - |
| encode | �~ | �����R�[�h | utf-8 |
| quote | �~ | �����蕶�� | " |
| delimiter | �~ | ��؂蕶�� | , |
| line_feed | �~ | ���s���� | \r\n |
| skip_initial_space | �~ | �J�����Ԃ̋󔒗L�� | False |
***
read_file():CSV�t�@�C����ǂݍ��݂܂��B

�߂�l�FList(yield)
***

### CsvFileWriter
#### CSV�t�@�C���쐬�@�\��ێ������N���X�ł��A�}���`�o�C�g�����ɂ��Ή����Ă��܂��B
***
__init__(file_path, encode='utf-8', quote='"', delimiter=',', line_feed='\r\n', skip_initial_space=False):

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| file_path | �� | �쐬������CSV�̃t�@�C���p�X | - |
| encode | �~ | �����R�[�h | utf-8 |
| quote | �~ | �����蕶�� | " |
| delimiter | �~ | ��؂蕶�� | , |
| line_feed | �~ | ���s���� | \r\n |
| skip_initial_space | �~ | �J�����Ԃ̋󔒗L�� | False |
***
write_file(fetch_data):CSV�t�@�C���𕡐��s�������݂܂��A�������ݏI����A�����Ńt�@�C�����N���[�Y���܂�

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| fetch_data | �� | �������݂������e�A���X�g�̃��X�g���w�肷�� | - |
�߂�l�F�Ȃ�
***
write_one_line(data):CSV�t�@�C�����P�s�������݂܂�

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| data | �� | �������݂������e�A���X�g���w�肷�� | - |
�߂�l�F�Ȃ�
***
close():CSV�t�@�C�����N���[�Y���܂�

�߂�l�F�Ȃ�
***

### ���̑����[�e�B���e�B
#### �f�B�N�V���i��
***
merge_dict(origin_dict, add_dict):�f�B�N�V���i���Ƀf�B�N�V���i�����}�[�W���܂��Adict.update�ƈႢ�A�f�B�N�V���i���̒��ɊY������L�[�����݂��Ȃ��ꍇ���ێ������܂܂ƂȂ�܂�

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| origin_dict | �� | �}�[�W���ƂȂ�f�B�N�V���i�� | - | 
| add_dict | �� | �}�[�W�Ώۂ̃f�B�N�V���i�� | - | 
�߂�l�F�}�[�W�����f�B�N�V���i��(dict)
***
replace_param_to_arg_dict(original_data, arg_dict):�f�B�N�V���i�������́u${�v�u}�v�ň͂܂ꂽ�l��u�����܂�

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| origin_dict | �� | �}�[�W���ƂȂ�f�B�N�V���i�� | - | 
| add_dict | �� | �u����� | - | 
�߂�l�F�Ȃ�
***

#### �t�@�C��
***
append_file(base_file_path, append_file_path):�t�@�C���Ƀt�@�C���̓��e��ǋL���܂�

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| base_file_path | �� | �ǋL��̃t�@�C�� | - | 
| append_file_path | �� | �ǋL���t�@�C�� | - | 
�߂�l�F�Ȃ�
***
get_file_lines(file_path):�t�@�C���̓��e���擾���܂�

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| file_path | �� | ���e���擾�������t�@�C���p�X | - | 
�߂�l�FList
***
get_file_line_cnt(file_path):�t�@�C���̍s�����擾���܂�

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| file_path | �� | �s�����擾�������t�@�C���p�X | - | 
�߂�l�F�t�@�C���s��(int)
***
grep_file(file_path, grep_str_list, output_file_path, file_code='utf-8', output_path='utf-8'):�t�@�C���̃O���b�v���ʂ𒊏o���܂�

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| file_path | �� | grep����t�@�C���p�X | - | 
| grep_str_list | �� | grep���镶����A�z��ŕ����w��ł��� | - |
| output_file_path | �� | grep���ʂ�f���o���t�@�C���p�X | - |
| file_code | �~ | grep����t�@�C���̕����R�[�h | utf-8 |
| output_path | �~ | grep���ʂ�f���o���t�@�C���̕����R�[�h | utf-8 |
�߂�l�F�Ȃ�
***
get_file_timestamp(file_path):�t�@�C���̃^�C���X�^���v���擾���܂�

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| file_path | �� | �^�C���X�^���v���擾�������t�@�C���p�X | - | 
�߂�l�F�^�C���X�^���v(datetime)
***
replace_file_contents(from_file_path, to_file_path, replace_dict):�t�@�C���̒��g��u�����܂�

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| from_file_path | �� | �u���������t�@�C���̃p�X | - |
| to_file_path | �� | �u�����ʂ��o�͂���t�@�C���̃p�X | - |
| replace_dict | �� | �u����� | - |
�߂�l�F�Ȃ�
***
get_dir_list(target_dir, include_hidden_folder=False):�w�肵���f�B���N�g�����ɑ��݂���f�B���Nt���̃��X�g���擾���܂�

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| target_dir | �� | �Ώۃf�B���N�g���̃p�X | - |
| include_hidden_folder | �~ | �B���t�H���_���܂߂邩�ۂ��B�܂߂�ꍇ��True��ݒ� | False |
�߂�l�F�f�B���N�g������(List)
***
get_file_path_list(target_folder_path, asc=True):�w�肵���f�B���N�g�����ɑ��݂���t�@�C���̃p�X���X�g���擾���܂�

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| target_folder_path | �� | �Ώۃf�B���N�g���̃p�X | - |
| asc | �~ | �t�@�C���̃^�C���X�^���v���~���̏�ԂŎ擾�������ꍇ��False��ݒ� | True |
�߂�l�F�f�B���N�g���p�X(List)
***
make_dirs(dir_path):���S�Ƀf�B���N�g�����쐬���܂�

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| dir_path | �� | �쐬�������f�B���N�g���̃p�X | - |
�߂�l�F�Ȃ�
***
interval_delete(target_folder_path, file_count):�w�肵���f�B���N�g�����ɑ��݂���t�@�C�����w�肵���������c���č폜����A�V�����t�@�C����D�悵�Ďc��

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| target_folder_path | �� | �Ώۃf�B���N�g���̃p�X | - |
| file_count | �� | �c���Ă��������t�@�C���� | - |
�߂�l�F�Ȃ�
***
interval_delete_folder(target_folder_path, leave_count):�w�肵���f�B���N�g�����ɑ��݂���f�B���N�g�����w�肵���������c���č폜����A�V�����f�B���N�g����D�悵�Ďc��

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| target_folder_path | �� | �Ώۃf�B���N�g���̃p�X | - |
| leave_count | �� | �c���Ă��������f�B���N�g���� | - |
�߂�l�F�Ȃ�
***
backup_file(file_path, target_dir):�w�肵���f�B���N�g���Ƀt�@�C�����R�s�[����A�R�s�[�����t�@�C���͎����I�Ƀt�@�C�����Ɏ��ԏ�񂪕t�^�����

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| file_path | �� | �o�b�N�A�b�v�������t�@�C���p�X | - |
| target_dir | �� | �o�b�N�A�b�v����f�B���N�g�� | - |
�߂�l�F�Ȃ�
***

#### gzip
***
compress_gzip(file_path, output_file_path=None):gzip�t�@�C���Ɉ��k����

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| file_path | �� | ���k�������t�@�C���̃p�X | - | 
| output_file_path | �~ | ���k��̃t�@�C���p�X�A���w��̏ꍇ��file_path+.gz�Ƃ����t�@�C���p�X�ɂȂ� | None | 
�߂�l�F�Ȃ�
***
un_gzip(file_path, output_file_path):gzip�t�@�C�����񓚂���

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| file_path | �� | �𓚂������t�@�C���̃p�X | - | 
| output_file_path | �� | �𓚌�̃t�@�C���p�X | - | 
�߂�l�F�Ȃ�
***
is_gzip(file_path):gzip�t�@�C�����ǂ������肷��

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| file_path | �� | �m�F�������t�@�C���̃p�X | - | 
�߂�l�F�Ȃ�
***

#### json
***
read_json_file(file_path, encoding='utf-8'):json�t�@�C����ǂݎ��Ajson�I�u�W�F�N�g���擾����

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| file_path | �� | �ǂݎ�肽��json�t�@�C���̃p�X | - | 
| encoding | �~ | �t�@�C���̕����R�[�h | utf-8 | 
�߂�l�Fjson�I�u�W�F�N�g(Dict)
***
write_json_file(file_path, data, encoding='utf-8'):json�I�u�W�F�N�g���t�@�C���ɗ��Ƃ����݂܂�

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| file_path | �� | �I�u�W�F�N�g��ۑ��������t�@�C���̃p�X | - |
| data | �� | �ۑ�������json�I�u�W�F�N�g | - |
| encoding | �~ | �t�@�C���̕����R�[�h | utf-8 | 
�߂�l�F�Ȃ�
***

#### ������
***
replace_str_by_dict_value(target_str, replace_dict):�Ώۂ̕�������w�肵���f�B�N�V���i���������ɒu������

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| target_str | �� | �u�������������� | - |
| replace_dict | �� | �u����� | - |
�߂�l�F�u����̕�����
***
get_string_width(target_str):�������𐔂���A�}���`�o�C�g��2�Ɗ��Z����

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| target_str | �� | �Ώە����� | - |
�߂�l�F������(int)
***
cut_string(target_str, length):��������J�b�g����A�}���`�o�C�g�������܂������ꍇ�͏��O�����

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| target_str | �� | �Ώە����� | - |
| length | �� | �J�b�g������������ | - |
�߂�l�F�J�b�g��������
***
to_camel_string(target):�X�l�[�N�P�[�X���L�������P�[�X�ɕϊ�����

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| target_str | �� | �Ώە����� | - |
�߂�l�F�L�������P�[�X������
***
convert_str(target):�I�u�W�F�N�g�𕶎���ɕϊ�����

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| target | �� | �ΏۃI�u�W�F�N�g | - |
�߂�l�F�ϊ�����������
***

#### zip
***
compress(compress_file_path, target_dir):�w�肵���f�B���N�g����zip�t�@�C���Ɉ��k����

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| compress_file_path | �� | ���k�t�@�C���̃p�X | - |
| target_dir | �� | ���k�������f�B���N�g���̃p�X | - |
�߂�l�F���k�t�@�C���̃p�X
***
compress_files(compress_file_path, target_file_path_list):�w�肵�������̃t�@�C����zip�t�@�C���Ɉ��k����

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| compress_file_path | �� | ���k�t�@�C���̃p�X | - |
| target_file_path_list | �� | ���k�����������̃t�@�C���p�X | - |
�߂�l�F���k�t�@�C���̃p�X
***
decompress(decompress_file_path, target_dir):zip�t�@�C�����𓀂���

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| decompress_file_path | �� | ���k�t�@�C���̃p�X | - |
| target_dir | �� | �𓀂������f�B���N�g���̃p�X | - |
�߂�l�F�𓀂��ꂽ�t�@�C���̃p�X(List)
***
compress_file(compress_file_path, target_file_path):�t�@�C����zip�t�@�C���Ɉ��k����

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| compress_file_path | �� | ���k�t�@�C���̃p�X | - |
| target_file_path | �� | ���k�������t�@�C���̃p�X | - |
�߂�l�F���k�t�@�C���̃p�X
***
compress_file_password(move_dir, compress_file_name, target_file_name, password):�Í������ꂽzip�t�@�C�����쐬����

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| move_dir | �� | ���k�t�@�C���̔z�u�f�B���N�g�� | - |
| compress_file_path | �� | ���k�t�@�C���̖��� | - |
| target_file_path | �� | ���k�������t�@�C���̃p�X | - |
| password | �� | �p�X���[�h | - |
�߂�l�F�Ȃ�
***
decompress_file(decompress_file_path, target_dir, target_file):���k���ꂽzip�t�@�C���̂Ȃ�����A����̃t�@�C���݂̂��𓀂���

| ���O | �K�{ | ���� | �f�t�H���g�l | 
|:-----------|:------------:|:-----------|:-----------| 
| decompress_file_path | �� | �𓀂������t�@�C���̃p�X | - |
| target_dir | �� | �𓀂����t�@�C����z�u����f�B���N�g�� | - |
| target_file | �� | �𓀂������t�@�C���̖��O| - |
�߂�l�F�𓀂����t�@�C���̃p�X
***

�֘A���
--------
1. [�O�O���J�X(�u���O)](http://gugurekasu.blogspot.jp/)
2. [LinkedIn](https://jp.linkedin.com/in/akirataniguchi1)
 
���C�Z���X
----------
Distributed under the [MIT License][mit].
[MIT]: http://www.opensource.org/licenses/mit-license.php
