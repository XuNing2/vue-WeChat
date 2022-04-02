<template>
    <div>
        <p>Using mustaches:{{ rawHtml }}</p>
        <p>
            Using v-html directive:
            <span v-html="rawHtml"></span>
        </p>
        <div class="main">
            <form class="input-group layui-form" lay-filter="filter_form">
                <div class="weui-cells__group weui-cells__group_form">
                    <div>申请流程</div>
                    <!-- <div class="step_box"><div class="step line"><img src="./apply_files/true.png"><span>提交</span></div><div class="step line"><img src="./apply_files/true.png"><span>院级审批</span></div><div class="step "><img src="./apply_files/true.png"><span>校级审批</span></div></div> -->
                    <div class="step_box">
                        <div class="step line">
                            <img src="./css/true.png" /><span>提交</span>
                        </div>
                        <div class="step line">
                            <img src="./css/true.png" /><span>院级审批</span>
                        </div>
                        <div class="step">
                            <img src="./css/true.png" /><span>校级审批</span>
                        </div>
                    </div>

                    <div class="weui-cells__title">外出信息</div>
                    <div class="weui-cells weui-cells_form">
                        <div class="info_list">
                            <div><span class="bt">*</span>开始日期</div>
                            <div class="form_select">
                                <div class="dOutStartDate info">
                                    2021-09-17
                                </div>
                                <span id="dOutStartDate">选择</span>
                            </div>
                        </div>

                        <div class="info_list">
                            <div><span class="bt">*</span>结束日期</div>
                            <div class="form_select">
                                <div class="dOutEndDate info">
                                    2021-09-17
                                </div>
                                <span id="dOutEndDate">选择</span>
                            </div>
                        </div>

                        <div class="info_list">
                            <div><span class="bt">*</span>外出地点</div>
                            <input
                                value="广州市海珠区万胜围"
                                type="text"
                                name="sOutAddress"
                                placeholder="-"
                                autocomplete="off"
                            />
                        </div>

                        <div
                            class="weui-input-row"
                            style="padding: 0 0.3rem 0.3rem 0.3rem"
                        >
                            <label class="smTitle"
                                ><span class="bt">*</span
                                ><span class="sNowAddr_required">外出事由</span>
                            </label>
                            <div class="weui-cell" style="padding: 0rem">
                                <div class="weui-cell__bd">
                                    <textarea
                                        class="weui-textarea"
                                        name="sOutReason"
                                        placeholder=""
                                        rows="3"
                                        style="border: 1px solid #efefef"
                                    >
                                    出外实习</textarea
                                    >
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="weui-cells__title">我的信息</div>
                    <div class="info_box">
                        <div class="info_list">
                            <span>姓名</span>
                            <input
                                type="text"
                                placeholder="-"
                                autocomplete="off"
                            />
                        </div>
                        <div class="info_list">
                            <span>学号</span>
                            <input
                                value="201830671024"
                                type="text"
                                placeholder="-"
                                autocomplete="off"
                            />
                        </div>
                        <div class="info_list">
                            <span>学院</span>
                            <input
                                type="text"
                                value="软件学院"
                                placeholder="-"
                                autocomplete="off"
                            />
                        </div>
                        <div class="info_list">
                            <span>年级</span>
                            <input
                                type="text"
                                value="2018"
                                placeholder="-"
                                autocomplete="off"
                            />
                        </div>
                        <div class="info_list">
                            <span>人员类型</span>
                            <input
                                type="text"
                                value="本科生"
                                placeholder="-"
                                autocomplete="off"
                            />
                        </div>
                    </div>

                    <div class="bottomTips">
                        温馨提示：每次只能发起一次外出申请，外出申请生效期间内无法再次发起申请。
                    </div>

                    <div class="btn_add" style="display: none">提交</div>
                    <div class="btn_cancel" style="display: none">撤销</div>
                </div>
            </form>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            rawHtml: "<span style='color: red'>This should be red.</span>",
        };
    },
};
</script>

<style>
@import "./css/weui.css";
</style>
