<template>
  <div class="form-config-container">
    <el-form label-position="left"
             label-suffix="："
             label-width="130px"
             size="small">
      <el-form-item label="表单名称">
        <el-input v-model="data.formName"
                  placeholder="表单名称"
        ></el-input>
      </el-form-item>
      <el-form-item label="表名">
        <el-input v-model="data.tableName"
                  placeholder="以online_form_开头"
        ></el-input>
      </el-form-item>
      <el-form-item label="标签对齐方式">
        <el-select v-model="data.labelPosition"
                   placeholder="标签对齐方式">
          <el-option label="左对齐"
                     value="left"></el-option>
          <el-option label="右对齐"
                     value="right"></el-option>
          <el-option label="顶部对齐"
                     value="top"></el-option>
        </el-select>
      </el-form-item>
      <el-form-item label="标签宽度">
        <el-input-number v-model="data.labelWidth"
                         :min="80"
                         :max="200"
                         :step="10"
                         controls-position="right"
                         placeholder="标签宽度"
                         style="width: 100%"></el-input-number>
      </el-form-item>
      <el-form-item label="标签后缀">
        <el-input v-model="data.labelSuffix"
                  placeholder="标签后缀"></el-input>
      </el-form-item>
      <el-form-item label="项之间的间隔">
        <el-input-number v-model="data.gutter"
                         :min="0"
                         :max="60"
                         :step="5"
                         controls-position="right"
                         placeholder="项之间的间隔"
                         style="width: 100%"></el-input-number>
      </el-form-item>
      <el-form-item label="多分组转标签">
        <el-switch v-model="data.tabs"
                   active-color="#409EFF"></el-switch>
      </el-form-item>
      <el-form-item label="详情模式">
        <el-switch v-model="data.detail"></el-switch>
      </el-form-item>
      <!-- <el-form-item label="标签样式"
                    v-if="data.tabs">
        <el-select v-model="data.tabsType">
          <el-option label="基础"
                     value=""></el-option>
          <el-option label="卡片"
                     value="card"></el-option>
          <el-option label="卡片2"
                     value="border-card"></el-option>
        </el-select>
      </el-form-item> -->
      <el-form-item label="显示按钮">
        <el-switch v-model="data.menuBtn"
                   active-color="#409EFF"></el-switch>
      </el-form-item>
      <!-- <el-form-item label="按钮位置"
                    v-if="data.menuBtn">
        <el-select v-model="data.menuPostion"
                   placeholder="按钮位置">
          <el-option label="居左"
                     value="left"></el-option>
          <el-option label="居中"
                     value="center"></el-option>
          <el-option label="居右"
                     value="right"></el-option>
        </el-select>
      </el-form-item> -->
      <el-form-item label="显示提交按钮"
                    v-if="data.menuBtn">
        <el-switch v-model="data.submitBtn"
                   active-color="#409EFF"></el-switch>
      </el-form-item>
      <!-- <el-form-item label="提交按钮的大小"
                    v-if="data.menuBtn && data.submitBtn">
        <el-select v-model="data.submitSize"
                   placeholder="提交按钮的大小">
          <el-option label="正常"
                     value="medium"></el-option>
          <el-option label="小"
                     value="small"></el-option>
          <el-option label="超小"
                     value="mini"></el-option>
        </el-select>
      </el-form-item> -->
      <el-form-item label="提交按钮的文字"
                    v-if="data.menuBtn && data.submitBtn">
        <el-input v-model="data.submitText"
                  placeholder="提交按钮的文字"></el-input>
      </el-form-item>

      <el-form-item label="显示清空按钮"
                    v-if="data.menuBtn">
        <el-switch v-model="data.emptyBtn"
                   active-color="#409EFF"></el-switch>
      </el-form-item>
      <!-- <el-form-item label="清空按钮的大小"
                    v-if="data.menuBtn && data.emptyBtn">
        <el-select v-model="data.emptySize"
                   placeholder="提交按钮的大小">
          <el-option label="正常"
                     value="medium"></el-option>
          <el-option label="小"
                     value="small"></el-option>
          <el-option label="超小"
                     value="mini"></el-option>
        </el-select>
      </el-form-item> -->
      <el-form-item label="清空按钮的文字"
                    v-if="data.menuBtn && data.emptyBtn">
        <el-input v-model="data.emptyText"
                  placeholder="提交按钮的文字"></el-input>
      </el-form-item>
      <el-form-item label="创建时间列表可见">
        <el-switch v-model="data.createTimeListView"></el-switch>
      </el-form-item>
      <el-form-item label="创建人列表可见">
        <el-switch v-model="data.createByListView"></el-switch>
      </el-form-item>
      <el-form-item label="更新时间列表可见">
        <el-switch v-model="data.updateTimeListView"></el-switch>
      </el-form-item>
      <el-form-item label="更新人列表可见">
        <el-switch v-model="data.updateByListView"></el-switch>
      </el-form-item>
      <el-form-item label="创建时间排序">
        <el-switch v-model="data.createTimeSort"></el-switch>
      </el-form-item>
      <el-form-item label="创建人排序">
        <el-switch v-model="data.createBySort"></el-switch>
      </el-form-item>
      <el-form-item label="更新时间排序">
        <el-switch v-model="data.updateTimeSort"></el-switch>
      </el-form-item>
      <el-form-item label="更新人排序">
        <el-switch v-model="data.updateBySort"></el-switch>
      </el-form-item>
      <el-form-item label="更新人搜索">
        <el-switch v-model="data.updateBySearch"></el-switch>
      </el-form-item>
      <el-form-item label="创建人搜索">
        <el-switch v-model="data.createBySearch"></el-switch>
      </el-form-item>
      <el-form-item label="创建时间搜索">
        <el-switch v-model="data.createTimeSearch"></el-switch>
      </el-form-item>
      <el-form-item label="更新时间搜索">
        <el-switch v-model="data.updateTimeSearch"></el-switch>
      </el-form-item>
      <el-form-item label="全局只读">
        <el-switch v-model="data.readonly"></el-switch>
      </el-form-item>
      <el-form-item label="全局禁用">
        <el-switch v-model="data.disabled"></el-switch>
      </el-form-item>
      <el-form-item label="业务字段">
        <el-switch v-model="data.busiStatus"></el-switch>
      </el-form-item>
      <!-- <el-form-item label="全局栅格">
        <el-input v-model="data.span"
                  placeholder="全局栅格"></el-input>
      </el-form-item> -->
    </el-form>
  </div>
</template>

<script>
export default {
  name: 'form-config',
  props: ['data']
}
</script>
